# Jenkins CI Setup for Student Portal (Simple Version)

## 1. Create a Jenkins Freestyle Job
- Open Jenkins → **New Item** → Freestyle project → name it **student-portal-site**.
- Under **Source Code Management → Git**:
  - Add your repo URL:  
    `https://github.com/YOUR_USERNAME/student-portal.git`
- Under **Build Triggers**:
  - Enable **GitHub hook trigger for GITScm polling**.
- Under **Build**:
  - Add "Execute shell" step with:
    ```
    echo "Building student portal"
    ls -la
    echo "Preview of index.html:"
    sed -n '1,50p' index.html
    ```

Save the job.

---

## 2. Set Up GitHub Webhook
On GitHub repo:
- Go to **Settings → Webhooks → Add webhook**
- Payload URL:
```
http://YOUR_JENKINS_SERVER/github-webhook/
```
- Content type: **application/json**
- Event: **Just the push event**
- Save.

---

## 3. Make a Small Update to the HTML File
```
git checkout -b tiny-update
```

Edit `index.html` (example: change heading or add a small comment).
```
git add index.html
git commit -m "Small update for Jenkins CI test"
git push -u origin tiny-update
git checkout main
git merge tiny-update
git push origin main
```

---

## 4. Jenkins Automatic Build (Expected)
When you push:

- GitHub sends a webhook to Jenkins.
- Jenkins job **student-portal-site** runs automatically.
- In Console Output you should see:
```
Building student portal
(file list)
Preview of index.html:

<h1>Event Registration - Updated</h1> Finished: SUCCESS ```
```
---


## 5. Verification

In GitHub: Settings → Webhooks → Recent Deliveries should show status 200.

In Jenkins: Build History shows a new automatic build triggered by your push.

Done ✔
This completes Jenkins CI setup with GitHub auto-trigger.
---

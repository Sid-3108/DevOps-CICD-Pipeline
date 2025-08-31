GitHub Webhook → Jenkins

This guide explains how to connect GitHub to Jenkins so builds happen **automatically** when you push code.

---

 🔌 Jenkins Configuration

1. Go to your Jenkins job (**hello-world**).  
2. Click **Configure**.  
3. Under **Build Triggers**, enable:  
   - ✅ **GitHub hook trigger for GITScm polling**  
4. Save.

---

🐙 GitHub Webhook Setup

1. Open your repo on GitHub.  
2. Go to **Settings → Webhooks → Add webhook**.  
3. Fill in:
   - **Payload URL**:  
     ```
     http://<JENKINS_PUBLIC_IP>:8080/github-webhook/
     ```
   - **Content type**: `application/json`  
   - Leave secret blank for this lab  
4. Click **Add webhook**.

---

 ✅ Test the Webhook

1. On your repo, edit a file (example: `hello.txt` or `index.html`).  
2. Commit & push to the branch Jenkins is watching (`dev` or `master`).  
3. Go to Jenkins → you should see a **new build triggered automatically**.

---

📌 Notes
- Webhook saves time → no need to click **Build Now** manually.  
- Make sure:
  - Jenkins server is accessible on port **8080** (open in SG)  
  - Your job is correctly configured with the GitHub repo URL + credentials  

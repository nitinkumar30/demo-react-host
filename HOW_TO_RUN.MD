So, today we'll see how to host our react-app in GitHub pages for free.

# Pre-requisites

- GitHub account
- Project created in react js
- Node installed
- Code Editor [VS Code preferred]

# Steps

1. First of all, install [node](https://nodejs.org/en/download/) in your system.

2. Navigate to your project root directory & open that in VS Code. First check whether node is installed in your system or not. Open New Terminal & put the command `npm --version`.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/enq9kpkeke3w8lh3z3ux.png)

3. Install the `gh-pages` npm package using following command - `npm install gh-pages --save-dev`

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/yxbmzzluiuhwhosd1e6q.png)

4. Now, login to your GitHub account & create a new repo with any name. I'm using **demo-react-host** for mine.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uezvhpqwduk5l17rle0l.png)



5. Navigate to VS Code now & open [package.json](package.json) file to edit the homepage property. The homepage's value should be in the format `https://{username}.github.io/{repo-name}`

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/me8nuruxywhqlulffk26.png)



6. Add deployement scripts to the same file.
```
"scripts": {
+   "predeploy": "npm run build",
+   "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
},
```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/u6e8vdfryqs9ufjt7i51.png)

7. Add the remote to local git repo by putting following command
```
git remote add origin https://github.com/{username}/{repo-name}.git
```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ptpq8b7naqrlcyhath6l.png)



8. Upload all the files to GitHub repo.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/aihgbhgo3vpahe7p37c0.png)


9. Deploy the site to GitHub repo using the command `npm run deploy`

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/k5jf6ciucbss7lav8rte.png)

10. Now, navigate to the link given in the "homepage" property of [package.json](package.json).  
You must see the homepage you've created.


---

**In case you're getting error while doing `remote origin` follow below:**

1. Just put following command
```
git remote rename origin upstream
```
; You can change name of upstream to any name[upstream1, upstream2 etc].

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/iq52uvk7gwurzg7ksoj9.png)


2. Then add new remote origin by putting following command
```
git remote add origin https://username.github.io/repo_name
```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pswetsrjbtbs0y9ob7xc.png)


3. Then, put the following command to push all commits
```
git push -u origin --all
```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/b2f06q8y5v951rxnet6r.png)

4. Now, deploy the site using following command
```
npm run deploy
```
It should result in status as 'Published' at the end.

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/2kghqj8w994lotxjpfq7.png)

5. Now, navigate to the link given in the "homepage" property of [package.json](package.json).  
You must see the homepage you've created.

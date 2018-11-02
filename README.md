# Upload Zoom Recordings to AWS S3 and YouTube

### Instructor Responsibilities
* Upload videos to corresponding staging area after each lecture.
* Create a `.txt` file containing information about the lecture and any resouces used.

### Resources and Description File
Please include information to be used in YouTube upload.

**Example:**
* **Lecture Title/Name:** Malware Traffic Analysis Review 
* **Date of Lecture:** Tuesday, October 30, 2018
* **Description:** Review of in class activity tracing source of malware download.
* **Tags:** cybersecurity, linux, malware, review, cyber, cohort 2
* **Resources:** any links or files used in lesson


### Uploading to S3 Staging Folder via AWS CLI
**Add alias to `~/.zshrc`:**
* add the following to the bottom of `.zshrc` file for cyber classes
    * ```
        # upload file to cyber-staging        
        alias upload-staging-cyber() {
            aws s3 cp $1 s3://devleague-instructor-videos/cyber-staging/$1 --profile devleague  
        }
        
        # view what is in staging folder
        alias cyber-staging="aws s3 ls s3://devleague-instructor-videos/cyber-staging/ --profile devleague"
    * remove `--profile devleague` flag if devleague account is your default
* add the following to the bottom of `.zshrc` file for JS Part Time classes
    * ```
        # upload file to js-pt-staging        
        alias upload-staging-jspt() {
            aws s3 cp $1 s3://devleague-instructor-videos/js-pt-staging/$1 --profile devleague  
        }
        
        # view what is in staging folder
        alias jspt-staging="aws s3 ls s3://devleague-instructor-videos/js-pt-staging/ --profile devleague"
    * remove `--profile devleague` flag if devleague account is your default
* add the following to the bottom of `.zshrc` file for JS Part Time classes
    * ```
        # upload file to js-ft-staging        
        alias upload-staging-jsft() {
            aws s3 cp $1 s3://devleague-instructor-videos/js-ft-staging/$1 --profile devleague  
        }
        
        # view what is in staging folder
        alias jsft-staging="aws s3 ls s3://devleague-instructor-videos/js-ft-staging/ --profile devleague"
    * remove `--profile devleague` flag if devleague account is your default
* run `source .zshrc` to evaluate commands added to the file

**Naming convention for S3 uploads:**
* `YYYY-MM-DD-Title_Of_Video_Or_Lecture.mp4` - for video files
* `YYYY-MM-DD-Title_Of_Video_Or_Lecture_Resources.txt` - for descriptions and resources for each video


### Uploading to YouTube
* Download file from S3 staging folder
* Upload file to YouTube
* ![youtube editor](https://www.github.com/zoom-uploads/assets/YouTube-Editing-View.png)
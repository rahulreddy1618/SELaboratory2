Below are **all answers completed clearly, correctly, and concisely**, formatted exactly to match your question numbers.

---

# ✅ **Scenario-Based Questions on Basic Git Commands**

---

### **1. Discard unstaged changes**

**Ans:**

```bash
git restore <file>
```

---

### **2. Remove a file from staging but keep changes**

**Ans:**

```bash
git restore --staged <file1.txt>
```

---

### **3. Fix last commit message (not pushed yet)**

**Ans:**

```bash
git commit --amend
```

---

### **4. View commit history in readable format**

**Ans:**

```bash
git log --oneline --graph --decorate --all
```

---

### **5. Set global name & email**

**Ans:**

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

---

### **6. View unstaged changes**

**Ans:**

```bash
git diff
```

---

### **7. Switch to feature/login branch**

**Ans:**

```bash
git switch feature/login
```

---

### **8. Recover deleted local branch (not pushed)**

**Ans:**

```bash
git reflog
git branch feature-ui <commit-hash>
```

---

### **9. Push local commits to remote**

**Ans:**

```bash
git push
```

---

### **10. Fetch changes without merging**

**Ans:**

```bash
git fetch
```

---

### **11. Create and switch to new branch search-filter**

**Ans:**

```bash
git switch -c search-filter
```

---

### **12. Remove file with API key from entire history**

**Ans:**

```bash
git filter-repo --path <file> --invert-paths
# then force push
git push --force --all
```

---

### **13. List both local and remote branches**

**Ans:**

```bash
git branch -a
```

---

### **14. Merge feature/signup into main**

**Ans:**

```bash
git merge feature/signup
```

---

### **15. Steps to resolve merge conflict**

**Ans:**

* Open conflicted file
* Remove conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
* Keep correct code
* Save file
* Stage & commit

```bash
git add file.txt
git commit
```

---

### **16. Prevent tracking of .log files & node_modules**

**Ans:**
Add to `.gitignore`:

```
*.log
node_modules/
```

---

### **17. Find who changed line 25 in script.py**

**Ans:**

```bash
git blame -L 25,25 script.py
```

---

### **18. Save work temporarily before switching branches**

**Ans:**

```bash
git stash
```

---

### **19. Restore stashed changes**

**Ans:**

```bash
git stash pop
```

---

### **20. Delete feature/test locally**

**Ans:**

```bash
git branch -d feature/test
```

---

### **21. Safely delete feature-ui after merge**

**Ans:**

```bash
git branch -d feature-ui
```

---

### **22. Force delete an unmerged branch**

**Ans:**

```bash
git branch -D feature-experiment
```

---

### **23. Requirement before deleting a branch**

**Ans:**
You **must not be on the branch you are deleting**.

---

### **24. Unsure if bugfix-footer is merged? Check first**

**Ans:**

```bash
git branch --merged
```

---

### **25. Delete feature-a, feature-b, feature-c in one command**

**Ans:**

```bash
git branch -d feature-a feature-b feature-c
```

---

# ✅ **Scenario-Based Questions on Remote Repositories**

---

### **1. Clone a remote repository**

**Ans:**

```bash
git clone <repo-url>
```

---

### **2. View remotes**

**Ans:**

```bash
git remote -v
```

---

### **3. Add a new remote**

**Ans:**

```bash
git remote add <name> <url>
```

---

### **4. Remove a remote**

**Ans:**

```bash
git remote remove <name>
```

---

### **5. Rename a remote**

**Ans:**

```bash
git remote rename <old> <new>
```

---

### **6. Fetch updates without merging**

**Ans:**

```bash
git fetch
```

---

### **7. Pull changes and merge them**

**Ans:**

```bash
git pull
```

---

### **8. Push local commits**

**Ans:**

```bash
git push
```

---

### **9. First-time push and set upstream**

**Ans:**

```bash
git push -u origin <branch>
```

---

### **10. Change remote URL**

**Ans:**

```bash
git remote set-url origin <new-url>
```

---

### **11. List remote branches**

**Ans:**

```bash
git branch -r
```

---

### **12. Remove deleted remote branches from local list**

**Ans:**

```bash
git fetch --prune
```

---

### **13. Fetch a specific branch**

**Ans:**

```bash
git fetch origin <branch>
```

---

### **14. Show detailed remote info**

**Ans:**

```bash
git remote show origin
```

---

### **15. Rebase local branch on remote**

**Ans:**

```bash
git pull --rebase
```

---




WEEK 3 lab 
---

# **WEEK 3 – Git Lab Workflow**

## **Objectives**

1. Demonstrate collaborative coding.
2. Resolve conflicts when collaborating on the same code.
3. Demonstrate creating and applying patches.
4. Scenario-based questions on Git workflow with remote repositories.

---

# **1. Collaborative Coding**

### **What is collaborative coding?**

Collaborative coding allows multiple people to work on the same codebase, share changes, review code, and improve quality together.

---

### **Two ways to collaborate**

1. **Creating an Organization**
2. **Collaborating through a shared repository**

---

### **A. Collaborative Work via GitHub Organization**

**Steps:**

1. Click **New Organization** → Create a free organization.
2. Enter organization details: name, email, verification. Click **Next**.
3. Add members to the organization. Members must **accept invitations**.
4. Set permissions:

   * `Settings → Member privileges → Base permissions → Write`
   * `Projects base permissions → Write`
5. Create a **remote repository** in the organization:

   * Can be private or public.
   * Accessible to all team members according to permissions.

---

### **B. Collaboration via Shared Repository**

**Collaborator 1 (Repository Owner)**

1. Go to `Settings → Collaborators → Manage Access → Add People`.
2. Invite collaborator 2; they must accept.

**Collaborator 2**

1. Set up Git and GitHub:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

2. Clone shared repo:

```bash
git clone https://github.com/username/repository-name.git
cd repository-name
```

3. Create a branch for your work:

```bash
git checkout -b feature/your-feature-name
```

4. Make changes and commit:

```bash
git add .
git commit -m "Descriptive commit message"
```

5. Push branch to GitHub:

```bash
git push origin feature/your-feature-name
```

6. Keep your branch updated:

```bash
git checkout main
git pull origin main
git checkout feature/your-feature-name
git merge main
```

---

### **C. Working via Fork**

**Scenario: Contributing to a public repository (Person 1)**

1. Fork repo → creates copy in your account (Person 2).
2. Clone fork locally:

```bash
git clone https://github.com/your-username/awesome-project
```

3. Make changes → `git add .` → `git commit` → `git push origin main`.
4. Create **Pull Request** back to original repo.
5. Person 1 reviews, merges PR → commit shows as Person 2’s changes, merged by Person 1.

**Tips:**

* Always pull latest changes before starting work:

```bash
git pull origin main
```

* Work in small, feature-specific branches.

---

# **2. Resolving Conflicts**

Conflicts occur when two collaborators change the same part of the code.

**Steps:**

1. Identify conflicts:

```bash
git status
```

2. Open conflicted file (`f1.txt`) → look for markers:

```python
def greet():
<<<<<<< HEAD
    print("Hello from First collaborator")
=======
    print("Hello from Second collaborator")
>>>>>>> feature/second-collaborator
```

3. Resolve conflict:

```python
def greet():
    print("Hello from First collaborator")
    print("Hello from Second collaborator")
```

4. Stage resolved file:

```bash
git add f1.txt
```

5. Complete merge:

```bash
git commit   # only if merging
git rebase --continue   # if rebasing
```

6. Abort merge if necessary:

```bash
git merge --abort
```

**Tips to avoid conflicts:**

* Pull latest changes before starting work: `git pull origin main`.
* Communicate with your team.
* Work on small, short-lived branches.

---

# **3. Creating and Applying Patches**

**What is a patch?**

* A patch is a text file representing changes between commits (`git diff` output).
* Can be emailed or shared to apply elsewhere.

**Steps:**

1. Make changes locally → commit.
2. Create patch:

```bash
git log   # get commit hash
git format-patch -1 <commit-hash>
```

* `-1` → one commit, generates `0001-commit-message.patch`
* Multiple commits: `git format-patch <base_commit>..HEAD`

3. Share patch file (email, chat, etc.).

**Apply patch (recipient):**

```bash
git apply 0001-commit-message.patch    # if plain patch
git am 0001-commit-message.patch       # if created via git format-patch
```

---

# **4. Scenario-Based Questions – Remote Repository**

**1. Error "rejected - non-fast-forward"**

```bash
git pull --rebase
git push
```

**2. Push feature branch without affecting main**

```bash
git push origin feature-branch
```

**3. Update local repo after remote changes**

```bash
git fetch --all
git pull origin main
```

**4. Pull changes while avoiding conflicts**

```bash
git stash       # save local changes
git pull origin main
git stash pop   # apply saved changes
```

**5. Sensitive file accidentally pushed**

* Remove file and rewrite history:

```bash
git filter-repo --path <file> --invert-paths
git push --force --all
```

* Rotate API key.

**6. Integrate latest main into feature branch**

```bash
git checkout feature-branch
git pull origin main --rebase
```

**7. Push to a different remote**

```bash
git remote add new-origin <new-url>
git push -u new-origin <branch>
```

**8. Local branch behind remote**

```bash
git fetch
git rebase origin/main
```

**9. Resolve conflicts with collaborators**

* Pull latest changes → resolve conflicts as described in Section 2.

**10. Delete remote branch**

```bash
git push origin --delete feature-branch
```

---




**Week 4 Maven Lab Action Plan**
---

**Notes:**

* `target/` is created after build (`mvn clean install`).

* Dependencies stored in local repo: `~/.m2/repository/groupId/artifactId/version/`.
---

## **2. Steps to Perform Maven Build and Testing**

**Command:**

```bash

mvn clean install

```



* **clean** → Deletes old build files (`target/` folder).

* **install** → Builds project, runs tests, installs artifact to local Maven repo.

**Check:**

* Compiled `.class` files in `target/`.

* JAR/WAR files in `target/`.

**Add dependency example (Gson):**
```xml

<dependency>

  <groupId>com.google.code.gson</groupId>

  <artifactId>gson</artifactId>

  <version>2.10</version>

</dependency>

``
---



## **3. Creating a Maven Java Project in Eclipse**



1. **Open Eclipse IDE** → File → New → Maven Project

2. **Choose Archetype:** `maven-archetype-quickstart`

3. **Configure metadata:**



   * GroupId: `com.example`

   * ArtifactId: `my-maven-project`

4. **Project structure generated:**



   * `src/main/java`, `src/test/java`, `pom.xml`

5. **Build and run:**



   * Right-click → Run As → Maven Clean / Install / Test / Build

6. **Run Java application:**



   * Right-click `App.java` → Run As → Java Application



---



## **4. Creating a Maven Web Project**



1. New Maven Project → Archetype: `maven-archetype-webapp`

2. Configure GroupId/ArtifactId

3. Add dependencies in `pom.xml` (Servlet, JSP, JSTL):



```xml

<dependency>

  <groupId>javax.servlet</groupId>

  <artifactId>javax.servlet-api</artifactId>

  <version>4.0.1</version>

  <scope>provided</scope>

</dependency>

```



4. Configure Tomcat server in Eclipse

5. Run Maven goals: `clean install test build`

6. Deploy WAR → Run on Server → Check output



---



## **5. Configuring Java Version**



**In `pom.xml`:**



```xml

<plugin>

  <groupId>org.apache.maven.plugins</groupId>

  <artifactId>maven-compiler-plugin</artifactId>

  <version>3.11.0</version>

  <configuration>

    <source>17</source>

    <target>17</target>

  </configuration>

</plugin>

```



**Check:**



```bash

mvn package

jar tf target/myapp.jar

```



---



## **6. JUnit Testing**



**Sample test (`AppTest.java`):**



```java

public class AppTest {

    @Test

    public void testSum() {

        assertEquals(5, 2 + 3);

    }

}

```
**Run tests:**

```bash

mvn test

```



**Check output:**



* `target/test-classes/` → compiled test classes

* `target/surefire-reports/` → test reports



---



## **7. Handling Errors in `pom.xml`**



* Typo in version numbers → BUILD FAILURE

* Missing repo → BUILD FAILURE

* Fix `pom.xml` and rerun:



```bash

mvn clean install

```



---



## **8. Adding Resource Files**



* Place in: `src/main/resources/config.properties`

* Access in code:



```java

InputStream input = getClass().getClassLoader().getResourceAsStream("config.properties");

```



* Check `target/classes/` → resources included



---



## **9. Multi-Module Maven Projects**



Structure:



```

parent/

 ├── pom.xml       → packaging: pom, lists modules

 ├── core/

 │    └── pom.xml

 └── web/

      └── pom.xml

```



* Parent defines `<modules>` and common dependencies

* Submodules build independently into `target/`



---



## **10. Executable JAR**



**pom.xml plugin:**



```xml

<plugin>

  <groupId>org.apache.maven.plugins</groupId>

  <artifactId>maven-jar-plugin</artifactId>

  <configuration>

    <archive>

      <manifest>

        <mainClass>com.example.Main</mainClass>

      </manifest>

    </archive>

  </configuration>

</plugin>

```



Build & run:



```bash

mvn package

java -jar target/myapp.jar

```



---



## **11. Building WAR Files**



* Web project structure: `src/main/webapp/WEB-INF/web.xml`

* Set `<packaging>war</packaging>` in `pom.xml`

* Build:



```bash

mvn package

```



* Output: `target/mywebapp.war` → deploy on Tomcat



---



## **12. Scenario-Based Questions (Quick Answers)**



1. **Compiler plugin error** → check `maven-compiler-plugin` version, run:



```bash

mvn clean compile -X

```



2. **Dependency not recognized** → verify `.m2` repo, run:



```bash

mvn dependency:tree

```



3. **Apply patch**:



```bash

git apply bugfix.patch

mvn clean install

```



4. **Rerun failed tests**:



```bash

mvn -Dtest=TestClassName#testMethod test

```



5. **Unsupported class version** → check `<source>` & `<target>` in `maven-compiler-plugin`.



6. **Change WAR → JAR** → set `<packaging>jar</packaging>` and configure `maven-jar-plugin`.



7. **Change build output dir** → in `pom.xml`:



```xml

<build>

  <directory>build_output</directory>

</build>

```



8. **Skip tests:**



```bash

mvn clean install -DskipTests

```



9. **Generate site report:**



```bash

mvn site

```



10. **Files generated after `mvn clean install`** → `target/` folder: `.class`, `.jar`/`.war`, reports.



11. **Dependency conflicts** → use `mvn dependency:tree` to check, use `<dependencyManagement>` to enforce versions.



12. **JUnit test run** → src/test/java, output in `target/test-classes` and `target/surefire-reports`.



13. **Executable JAR** → `maven-jar-plugin`, set `mainClass`.



14. **Custom JAR**:



```bash

mvn install:install-file -Dfile=path/to/lib.jar -DgroupId=com.example -DartifactId=library -Dversion=1.0.0 -Dpackaging=jar

```



15. **Maven web project (WAR)** → `src/main/webapp`, `WEB-INF`, `<packaging>war</packaging>`.



16. **Build WAR** → `mvn clean install`, deploy to Tomcat: `target/mywebapp.war`.



17. **Add JSTL & servlet-api** → servlet-api scope `provided` (server provides it).



18. **Multi-module project** → parent pom defines modules, dependencies shared, each module builds to `target/`.



19. **Maven web project config vs traditional WAR** → Maven handles dependencies, build, test, and package automatically; execution via Tomcat remains same.

---



week 7
## **1. Define and Run Multiple Interdependent Services**

**Folder & `docker-compose.yml`:**

```yaml
version: "3.9"
services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"

  db:
    image: postgres:15
    environment:
      POSTGRES_USER: demo
      POSTGRES_PASSWORD: demo
      POSTGRES_DB: demo_db
```

**Run:**

```bash
docker compose up -d
```

* Visit [http://localhost:8080](http://localhost:8080) → Nginx welcome page.
* `db` container runs in the background.

---

## **2. Add Redis Cache and `depends_on`**

**Updated `docker-compose.yml`:**

```yaml
services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"
    depends_on:
      - redis

  db:
    image: postgres:15
    environment:
      POSTGRES_USER: demo
      POSTGRES_PASSWORD: demo
      POSTGRES_DB: demo_db

  redis:
    image: redis:alpine
```

**Restart services:**

```bash
docker compose up -d
docker compose ps
```

✅ All three services (`web`, `db`, `redis`) should be running.

---

## **3. Deploy Across Different Machines**

1. Zip your `compose-lab` folder.
2. Transfer to another machine with Docker Compose.
3. Run:

```bash
docker compose up -d
```

* Output: same services run on the new machine without changes.

---

## **4. Networking and Persistent Storage**

**Update `docker-compose.yml` for network & volume:**

```yaml
networks:
  app-net:

volumes:
  db-data:

services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"
    networks:
      - app-net
    depends_on:
      - db

  db:
    image: postgres:15
    environment:
      POSTGRES_USER: demo
      POSTGRES_PASSWORD: demo
      POSTGRES_DB: demo_db
    volumes:
      - db-data:/var/lib/postgresql/data
    networks:
      - app-net
```

**Run:**

```bash
docker compose up -d
```

**Insert data into Postgres using `psql`:**

```bash
docker exec -it compose-lab-db-1 psql -U demo -d demo_db

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(50),
    email VARCHAR(100)
);

INSERT INTO users (name, email) VALUES
('Alice', 'alice@example.com'),
('Bob', 'bob@example.com');

SELECT * FROM users;
```

* Stop & remove containers: `docker compose down`
* Start again: `docker compose up -d` → data persists via `db-data` volume.

---

## **5. Faster Iteration During Development (Flask Example)**

**`app.py`:**

```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def home():
    return "Hello from Flask + Docker!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

**Dockerfile:**

```dockerfile
FROM python:3.10-slim
WORKDIR /app
COPY app.py /app/
RUN pip install flask
CMD ["python", "app.py"]
```

**`docker-compose.yml` update:**

```yaml
web:
  build: .
  ports:
    - "5000:5000"
  depends_on:
    - db
```

**Run:**

```bash
docker compose up --build
```

* Visit [http://localhost:5000](http://localhost:5000)
* Modify `app.py` → rebuild with `docker compose up --build` → see changes instantly.

---

## **Scenario-Based Questions & Answers**

1. **Multiple apps in same container?**
   ❌ Not recommended. One container = one process. Use multiple containers instead.

2. **Expose Flask + Nginx on same host:**

   * Flask: `ports: "5000:5000"`
   * Nginx: `ports: "80:80"` → each container uses different host ports.

3. **React frontend, Express backend, MongoDB:**

   * Use `docker-compose.yml` → define 3 services.
   * Use networks to allow service-to-service communication.

4. **Two containers exposing port 8080:**
   ❌ Conflict → use different host ports (`8081:8080`, `8082:8080`) or separate hosts.

5. **Restart all containers after code update:**

```bash
docker compose restart
```

6. **Update only frontend:**

```bash
docker compose up -d --build web
```

7. **Tomcat on 8080 “Connection Refused”:**

   * Container not running, or firewall blocking. Check `docker ps` and ports.

8. **Check container using port 3000:**

```bash
docker ps
docker port <container_name>
```

9. **Stop & remove Tomcat container & image:**

```bash
docker stop <container_name>
docker rm <container_name>
docker rmi <image_name>
```

10. **Share app with teammate:**

    * Build image → push to Docker Hub:

```bash
docker tag my-app username/my-app:latest
docker push username/my-app:latest
```

---

## **✅ Conclusion**

Docker Compose:

* Simplifies multi-container app management
* Defines, configures, and runs services in a single YAML
* Ensures consistent environments across machines
* Supports persistent storage, networking, and faster development iterations

---



---

## **1. Working with Docker CLI Commands (Redis)**

### **Step 1: Pull the Redis Image**

```bash
docker pull redis
```

* Downloads the latest Redis image from Docker Hub to your local system.

### **Step 2: Run a Redis Container**

```bash
docker run --name my-redis -d redis
```

* `--name my-redis`: names the container.
* `-d`: runs it in the background.

### **Step 3: Check Running Containers**

```bash
docker ps
```

* Lists all active containers.

### **Step 4: Access Redis CLI**

```bash
docker exec -it my-redis redis-cli
```

* Opens Redis CLI inside the container.
* Example commands:

```redis
SET name "Alice"
GET name
```

### **Step 5: Stop the Redis Container**

```bash
docker stop my-redis
```

* Stops container without deleting it.

### **Step 6: Restart the Container**

```bash
docker start my-redis
```

### **Step 7: Remove the Container**

```bash
docker rm my-redis
```

### **Step 8: Remove the Redis Image**

```bash
docker rmi redis
```

---

## **2. Working with Dockerfile (Custom Redis Image)**

### **Step 1: Set Up Folder**

**Windows:**

```bash
mkdir C:\DockerProjects\Redis
cd C:\DockerProjects\Redis
```

**Mac/Linux:**

```bash
mkdir ~/DockerProjects/Redis
cd ~/DockerProjects/Redis
```

### **Step 2: Write Dockerfile**

Create a file named `Dockerfile`:

```dockerfile
FROM redis:latest
CMD ["redis-server"]
```

---

### **Docker Commands Step-by-Step**

1. **Build a Docker Image**

```bash
docker build -t redisnew .
```

* Builds an image from Dockerfile.
* `-t redisnew` names it.

2. **Run Container from Custom Image**

```bash
docker run --name myredisnew -d redisnew
```

3. **Check Running Containers**

```bash
docker ps
```

4. **Stop Container**

```bash
docker stop myredisnew
```

5. **Login to Docker Hub**

```bash
docker login
```

6. **Show All Containers**

```bash
docker ps -a
```

7. **Commit Changes to a New Image**

```bash
docker commit 0e993d2009a1 budarajumadhurika/redis1
```

* Saves current container as a new image.

8. **List All Images**

```bash
docker images
```

9. **Push Image to Docker Hub**

```bash
docker push budarajumadhurika/redis1
```

10. **Remove Container**

```bash
docker rm 0e993d2009a1
```

11. **Remove Image**

```bash
docker rmi budarajumadhurika/redis1
```

12. **Verify All Containers**

```bash
docker ps -a
```

13. **Logout from Docker Hub**

```bash
docker logout
```

14. **Pull Image from Docker Hub**

```bash
docker pull budarajumadhurika/redis1
```

15. **Run Container from Pulled Image**

```bash
docker run --name myredis -d budarajumadhurika/redis1
```

16. **Access Redis CLI**

```bash
docker exec -it myredis redis-cli
```

17. **Set and Get Key-Value**

```redis
SET name "Abcdef"
GET name
```

18. **Exit Redis CLI**

```bash
exit
```

19. **Check Container Status**

```bash
docker ps -a
```

20. **Stop Container**

```bash
docker stop myredis
```

21. **Remove Container**

```bash
docker rm 50a6e4a9c326
```

22. **List Images**

```bash
docker images
```

23. **Remove Image**

```bash
docker rmi budarajumadhurika/redis1
```

24. **Optional: Logout**

```bash
docker logout
```

---

### **✅ Key Takeaways**

* Docker CLI commands let you **pull, run, stop, remove, and manage containers** easily.
* `docker build` + Dockerfile allows you to create **custom images**.
* `docker commit` can snapshot container changes into a new image.
* Docker Hub enables **sharing images** across machines and teams.
* Containers are **isolated but lightweight**, and images can be versioned and reused.

---




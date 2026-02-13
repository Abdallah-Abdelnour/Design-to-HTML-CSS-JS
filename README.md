# Landing Page CI/CD avec Jenkins et Docker

## 🏗️ Description du projet
Ce projet met en place un **pipeline CI/CD automatisé** pour une landing page web.  
À chaque modification du code sur GitHub (`git push`), Jenkins :

1. Récupère le code depuis GitHub
2. Build l’image Docker de l’application
3. Push l’image Docker sur DockerHub
4. Déploie automatiquement la nouvelle version

Le projet démontre l’utilisation de **GitHub, Docker, Jenkins, Jenkins Pipeline, Webhook et DockerHub**, ainsi que la **gestion sécurisée des credentials**.

---

## 🛠️ Technologies utilisées

- **GitHub** : Hébergement du code et du Dockerfile/Jenkinsfile
- **Jenkins** : Automatisation du pipeline CI/CD
- **Docker** : Conteneurisation de l’application
- **DockerHub** : Stockage des images Docker
- **Webhook GitHub** : Déclenchement automatique du pipeline
- **Jenkins Credentials** : Gestion sécurisée des tokens pour DockerHub et GitHub

---

## 📂 Structure du projet

landing-page/
├── fichier de application web # 
├── Dockerfile # Création de l'image Docker
├── Jenkinsfile # Pipeline CI/CD
└── README.md # Documentation


---

## ⚙️ Installation et utilisation

1. Cloner le repo :

```bash
git clone https://github.com/Abdallah-Abdelnour/Design-to-HTML-CSS-JS.git
cd Design-to-HTML-CSS-JS

2. Lancer Jenkins sur une VM ou un serveur :
Via Docker :

docker run -d \
  -p 8080:8080 \
  -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  --name jenkins \
  jenkins/jenkins:lts

3. Ajouter credentials DockerHub et GitHub token dans Jenkins

4. Créer un Pipeline Job et lier le repo GitHub avec le Jenkinsfile

5. Vérifier le pipeline : chaque git push déclenche automatiquement le build et le push DockerHub

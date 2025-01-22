# Git

## 1. Instalación y configuración de Git
EN GIT BASH
(Cambiar user la pestaña User Settings en Preferences/Version Control(Team)/Git/Configuration 
Deben ser user.email y user.name de la cuenta asociada a github)


### 1.1. Instalar git en local
	https://git-scm.com/downloads

### 1.2. Configurar user y email
Abrir terminal de git bash.

	git config --global user.name "TuNombre" 
	git config --global user.email "TuCorreo@example.com"

### 1.3. Crear cuenta en gitHub / GitLab
	https://github.com/
	https://gitlab.com/

### 1.4. Claves SSH
#### 1.4.1 Crear claves (2 tipos): 
	RSA: 	ssh-keygen -t rsa -b 4096 -C "correo vinculado a github"
	ED: 	ssh-keygen -t ed25519 -C "correo vinculado a github"
		
Se generan una pública y una privada: (carpeta usuario/.ssh)

	ls ~/.ssh
	
#### 1.4.2 Iniciar agente ssh en terminal
	eval $(ssh-agent -s) 
	
#### 1.4.3 Añadir la clave privada al agente
	ssh-add ~/.ssh/id_rsa
	ssh-add ~/.ssh/id_ed25519
		
#### 1.4.4 Añadir clave pública a GitHub / GitLab
- Consultar su contenido:

		cat ~/.ssh/id_rsa.pub
		cat ~/.ssh/id_ed25519.pub

- Añadir clave a GitHub

		Conf GitHub -> Claves SSH y GPG -> new SSH key -> Copiar la clave aquí
	
## 2. Crear nuevo repositorio
- Clonar repositorio remoto
- Subir repositorio desde local
- Crear desde la web

### 2.1 Opción 1

#### 2.1.1 Inicializar en un repositorio en local
	git init en la carpeta deseada (se crea .git)

#### 2.1.2. Vincular el rep local al repositorio remoto
	https:	git remote add origin https://github.com/usuarioGitHub/(rep de github creado anteriormente).git 
	ssh: 	git remote add origin git@github.com:usuarioGitHub/repositorio.git
	
#### 2.1.2 Cambiar rama principal (main)
	git branch -M nombre_branch
	
#### 2.1.3 Subir repo local a remoto
	git add .
	git commit -m "Mensaje (Primer commit)"
	git push 

### 2.2 Opción 2	

#### 2.2.1 Clonar repositorio remoto a local (se vincula automáticamente)
	git clone git@github.com:usuarioGitHub/repositorio.git
	

## 3. Trabajar con Git

### 3.1 fichero .gitignore
		
### 3.2 Subir cambios al remoto
#### 3.2.1 Visualizar archivos modificados
		git status 
			
#### 3.2.2 Añadirlos a cambios preparados
		git add .
		git add fichero/carpeta 
		
#### 3.2.3 Hacer commit
		git commit -m "mensaje" 
			
#### 3.2.4 Enviar cambios a repositorio remoto
		git push 
		git push origin nombre_Rama
	
### 3.3 Bajar cambios del remoto (creados por otros usuarios)
#### 3.3.1 consultar si hay cambios en el remoto (no modifica local)
		git fetch 
		
#### 3.3.2 Aplicar cambios al local
		git pull
		git pull origin nombre_Rama
	
### 3.4 Ramas
#### 3.4.1 Crear rama sin moverse a ella
		git branch nombre_Rama
			
#### 3.4.2 Crear rama y moverse a ella
		git checkout -b nombre_Rama
			
#### 3.4.3 Ver ramas (locales y remotas)
		git branch -a
			
#### 3.4.4 Eliminar rama
		git branch -d nombre_Rama
			
#### 3.4.5 Fusionar ramas
		git merge nombre_Rama
		
#### 3.4.6 Subir rama a remoto
		git push origin nombre_Rama
Se crea un merge / pull request que se gestiona en GitLab / GitHub respectivamente

## 4. Enlaces
	Curso 5h Git / GitHub
	https://youtu.be/3GymExBkKjE?si=WDLEVRnUVZFJV3zD

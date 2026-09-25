## Instrucciones de Ejecución

### 1. Ejecución Local

* **Entorno de Desarrollo:**
  ```bash
  npm run dev
  ```

  * **Ejecutar pruebas automatizadas:**
  ```bash
  npm test
  ```

### 2. Ejecución con Docker Compose

* **Entorno Development:**
	```bash
	docker compose --profile dev up --build
	```

	-Levanta el contenedor de desarrollo. Acceso disponible en: http://localhost:3000/api/info

* **Entorno Test:**
	```bash
	docker compose --profile test up --build --abort-on-container-exit --exit-code-from app-test
	```

	-Ejecuta las pruebas automatizadas dentro de Docker y finaliza el contenedor con código 0 al aprobar todas.

* **Entorno Production:**
	```bash
	docker compose --profile prod up --build -d
	```

	-Levanta el contenedor de producción en segundo plano. Acceso disponible en: http://localhost:8080/api/info

### 3. Detener Servicios Docker
	-Para detener y limpiar los contenedores de un perfil específico:
	```bash
	docker compose --profile dev down
	docker compose --profile test down
	docker compose --profile prod down
	```
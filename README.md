# nachet-backend

## High level sequence diagram
![SD_1 drawio (2)](https://github.com/ai-cfia/nachet-backend/assets/19809069/272f37dc-f4ec-449b-ba82-950c54b9f856)

**Details**

- The backend was built with the [Quart](http://pgjones.gitlab.io/quart/) framework
- Quart is an asyncio reimplementation of Flask
- All HTTP requests are handled in `app.py` in the root folder
- Azure Storage API calls are handled in the `azure_storage_api/azure_Storage_api.py
- Inference results from model endpoint are directly handled in `model_inference/inference.py`

****
 
### RUNNING NACHET-BACKEND FROM DEVCONTAINER
When you are developping, you can run the program while in the devcontainer by using this command:
```
hypercorn -b :8080 app:app
```

### RUNNING NACHET-BACKEND AS A DOCKER CONTAINER
If you want to run the program as a Docker container (e.g., for production), use: 
```
docker build -t nachet-backend .
docker run -p 8080:8080 -v $(pwd):/app nachet-backend
```

### TESTING NACHET-BACKEND
To test the program, simply run the `run_tests.py` file.
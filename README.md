# COMO INICIAR O PROJETO PARA DUMBS

## Getting Started

First, run the backend development server:

```bash
cd backend
python -m venv venv
source ./venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

next times

```bash
cd backend
source ./venv/bin/activate
uvicorn main:app --reload
```

Open [http://localhost:8000/](http://localhost:8000/) with your browser to see swagger.


First, run the frontend development server:

```bash
cd frontend
npm install
npm run dev
```

next times

```bash
cd frontend
npm run dev
```

Open [http://localhost:5173/](http://localhost:5173/) with your browser to page.

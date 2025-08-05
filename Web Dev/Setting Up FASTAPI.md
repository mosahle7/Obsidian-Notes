
py -3 -m venv venv

**Python Interpreter:** .\venv\Scripts\python.exe

venv\Scripts\activate.bat
.\venv\Scripts\Activate.ps1


pip install fastapi[all]

uvicorn app.main:app --reload


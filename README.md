# matrice

## Requirements
* [mysql](https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/8.2.0/xampp-windows-x64-8.2.0-0-VS16-installer.exe/download)
* [npm (you can probably use yarn)](https://www.npmjs.com/)
* [pip](https://pip.pypa.io/en/stable/installation/)
* [MUI](https://mui.com/material-ui/getting-started/installation/)


## Installation
```
1. Download this repo and place it in your desired dir.
2. Cd to valde then run 'npm install'.
3. Setup mysql (xampp) and start MySQL.
4. Run the sql from sql.sql in mysql (i know many sql's in that sentence).
5. Install flask (pip)
```

## Usage
1. Open to terminals at the root of the project.
2. At terminal one cd to valde and type `npm start` (to start the client).
3. At terminal 2 cd to server and type `py main.py` (not sure if it works on linux and or mac).

## Config
**Server**

Change database to the name of the database you are using if you do not wish to use the one provided in `sql.sql`
```python
dbconfig = {
  "database": "valde",
  "user":     "root",
  "host":     "localhost" # if database is not running locally, host should be the ip of the database server. 
}
```

**Client**

Go to `valde/src/App.tsx` and configure below.
```typescript
function getData() {
    fetch("http://localhost:5000/members").then( // localhost should be the server ip if you are not using your not testing on a local machine.
      res => res.json()
    ).then(
      data => {
        console.log(data)
        setdata(data)
      }
    )
  }
```

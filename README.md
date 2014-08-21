go-orm
======

ORM with No-SQL

Deployment
==========

    1 . Download the package
    2 . Extract the file and paste it in to $GOROOT/src/pkg/
    3 . cd $GOROOT/src/pkg/go-orm-noschema/src/db/
    4 . go install (It will create $GOROOT/pkg/linux_amd64/go-orm-noschema/src/db.a file)

Example 
=======
package main

import (
            "go-orm-noschema/src/db"
            "fmt"
)

func main() {
        database := db.GetConnection("config.ini") //Pass configuration file location
        record := db.NewRecord()

        //Save
        record.Set("student.name", "suriya")
        record.Set("student.mark", 52)
        record.Set("student.age", 24)
        record.Set("employee.name", "williams")
        database.Save(record)

        //Read
        a := database.Read()
        fmt.Println(a)

        //Update
        //a[0].Set("student.communication.telephone","2332348")
        //database.Update(a[0])

        //Delete
        //database.Delete(a[0])
}

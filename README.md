"([A-Za-z]{3}[A-Za-z]* [A-Za-z]{3}[A-Za-z]*)|([A-Za-z]+'[A-Za-z]*[A-Za-z]{3}[A-Za-z])";












import {Component} from '@angular/core';

@Component({
    selector:'add-emp',
    templateUrl:'app.emp.html'

})

export class Employee{
    empId:number;
    empName:string;
    empSalary:number
    empDepartment:string
    empjoining:string   

    empall:any=[
        {empId:1001,empName:"ABCD",empSalary:3334.58,empDepartment:"Java",empjoining:'6/12/2014'},
        {empId:1002,empName:"ABC",empSalary:1000.45,empDepartment:"C",empjoining:'6/12/2014'},
        {empId:1003,empName:"AB",empSalary:1254.65,empDepartment:"Testing",empjoining:'6/12/2014'},
        {empId:1004,empName:"A",empSalary:3589.45,empDepartment:"Sap",empjoining:'6/12/2014'},
        {empId:1006,empName:"BCD",empSalary:4521.25,empDepartment:"Core Java",empjoining:'6/12/2014'},
        {empId:1007,empName:"CD",empSalary:4289.13,empDepartment:"Testing",empjoining:'6/12/2014'},
        {empId:1005,empName:"D",empSalary:8965.74,empDepartment:"Sap",empjoining:'6/12/2014'},
        {empId:1010,empName:"AD",empSalary:7544.99,empDepartment:".net",empjoining:'6/12/2014'},
        {empId:1009,empName:"BC",empSalary:3698.58,empDepartment:"BI",empjoining:'6/12/2014'}
    ];

    sortId():any{
        this.empall.sort(function(a,b):any{
            if((a.empId-b.empId)>0) return 1;
            else if((a.empId-b.empId)<0) return -1;
            else return 0;
        })
    }

    sortName():any{
        this.empall.sort(function(a,b):any{
            if(a.empName.toLowerCase()>b.empName.toLowerCase()) return 1;
            else if(a.empName.toLowerCase()<b.empName.toLowerCase()) return -1;
            else return 0;
        })
    }

    sortSalary():any{
        this.empall.sort(function(a,b):any{
            if((a.empSalary-b.empSalary)>0) return 1;
            else if((a.empSalary-b.empSalary)<0) return -1;
            else return 0;
        })
    }

    sortDepartment():any{
        this.empall.sort(function(a,b):any{
            if(a.empDepartment.toLowerCase()>b.empDepartment.toLowerCase()) return 1;
            else if(a.empDepartment.toLowerCase()<b.empDepartment.toLowerCase()) return -1;
            else return 0;
        })
    }
}





<h2>Show all Employee</h2>
<table border="1">
    <tr>
        <th><a href="#" (click)="sortId()">ID</a></th>
        <th><a href="#" (click)="sortName()">Name</a></th>
        <th><a href="#" (click)="sortSalary()">Salary</a></th>
        <th><a href="#" (click)="sortDepartment()">Department</a></th>
        <th><a href="#" (click)="sortDate()">Date</a></th>
    </tr>
    <tr *ngFor="let data of empall">
        <td>{{data.empId}}</td>
        <td>{{data.empName}}</td>
        <td>{{data.empSalary}}</td>
        <td>{{data.empDepartment}}</td>
        <td>{{data.empjoining}}</td>
    </tr>
</table>

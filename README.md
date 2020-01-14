# Join 2 list with linq:

        var res = from e1 in emp1 
                    join e2 in emp2 
                        on e1.emp_id equals e2.emp_id 
                            select new 
                            { 
                                Emp_Name = e1.emp_name, 
                                Emp_Salary = e2.emp_salary 
                            }; 


        var res = emp1.Join(emp2, 
                            e1 => e1.emp_id, 
                            e2 => e2.emp_id, 
                            (e1, e2) => new { 
                                EmployeeName = e1.emp_name, 
                                EmployeeDepartment = e2.emp_dept }); 

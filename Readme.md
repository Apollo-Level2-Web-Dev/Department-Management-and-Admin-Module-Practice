# Practice Task: Complete Management Department & Admin Module

Do not forget to add routes in `routes/index.ts` file.

### Create routes, controllers, services, constants, validation, utils for the management department module given below. 

#### Root route should be `api/v1/management-departments`.

```typescript
router.post(
  '/create-management',  
  validateRequest(ManagementDepartmentValidation.createManagementDepartmentZodSchema),
  ManagementDepartmentController.createManagementDepartment
);

router.get('/', ManagementDepartmentController.getAllManagementDepartments);

router.get('/:id', ManagementDepartmentController.getSinglelManagementDepartment);

router.patch(
  '/:id',
  validateRequest(ManagementDepartmentValidation.updateManagementDepartmentZodSchema),
  ManagementDepartmentController.updateManagementDepartment
);
```

### Create routes, controllers ,services,constants,validation , utils for  the admin module  given below

#### Root route should be `api/v1/users`.

```typescript
router.post(
  '/create-admin',
  validateRequest(AdminValidatio.createAdminZodSchema),
  AdminController.createAdmint)
);
```
### Things to do

- Generate a utility function to create admin incremental id. Pattern `A-00001`

#### Root route should be `api/v1/admins`.

```typescript
router.get('/',AdminController.getAllAdmins);

router.get('/:id', AdminController.getSingleAdmin);

router.patch(('/:id', 
  validateRequest(AdminValidation.updateAdminZodSchema),
  AdminController.updateAdmin
);
```

# Model

### Management Department
- _id
- title
- createdAt
- updatedAt

#### Sample Data

```json
{
    "_id": "6473c6a50c56d0d40b9bb6a3",
    "title": "Account Management",
    "createdAt": "2023-05-28T21:24:53.677Z",
    "updatedAt": "2023-05-28T21:24:53.677Z"
}
```

### Admin
- _id: ObjectID
-  id: string;
-  name:
    -  firstName
    -  middleName (optional)
    -  lastName
-  dateOfBirth
-  email
-  contactNo
-  emergencyContactNo
-  gender
-  permanentAddress  
-  presentAddress
-  bloodGroup (optional)
-  managementDepartment
-  designation
-  profileImage (optional)
-  createdAt
-  updatedAt

#### Sample Data

```json
{
  "id": "A-00002",
  "name": {
    "firstName": "kader",
    "lastName": "khan",
    "middleName": "ahmed"
  },
  "dateOfBirth": "1990-02-07",
  "gender": "male",
  "bloodGroup": "AB+",
  "email": "kader@gmail.com",
  "contactNo": "01800000006",
  "emergencyContactNo": "01800000006",
  "presentAddress": "asf",
  "permanentAddress": "asdf",
  "managementDepartment": "6473c6a50c56d0d40b9bb6a3",
  "designation": "HR executive",
  "profileImage": "https://via.placeholder.com/150x150",
  "createdAt": "2023-05-31T14:42:22.747Z",
  "updatedAt": "2023-06-01T08:54:57.058Z"
}
```


#### Sample Data (After Populate)

```json
{
  "id": "A-00002",
  "name": {
    "firstName": "kader",
    "lastName": "khan",
    "middleName": "ahmed"
  },
  "dateOfBirth": "1990-02-07",
  "gender": "male",
  "bloodGroup": "AB+",
  "email": "kader@gmail.com",
  "contactNo": "01800000006",
  "emergencyContactNo": "01800000006",
  "presentAddress": "asf",
  "permanentAddress": "asdf",
  "managementDepartment": {
    "_id": "6473c6a50c56d0d40b9bb6a3",
    "title": "Account Management",
    "createdAt": "2023-05-28T21:24:53.677Z",
    "updatedAt": "2023-05-28T21:24:53.677Z"
  },
  "designation": "HR executive",
  "profileImage": "https://via.placeholder.com/150x150",
  "createdAt": "2023-05-31T14:42:22.747Z",
  "updatedAt": "2023-06-01T08:54:57.058Z"
}
```

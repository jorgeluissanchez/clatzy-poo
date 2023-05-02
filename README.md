# **Plan:**
Este es el plan de desarrollo el cual sigo para el desarrollo de la [actividad de POO](https://drive.google.com/file/d/1iJxXS0GNKhhgiayXDoGZHemrAvA8W3c4/view?usp=sharing)

## **Clases Generales:**
- Clatzy 🏋️‍♂️
- Cliente 👤
- Instructor 👨‍🏫
- Persona 👤
- Curso 📚
- PlanCliente 💳
- ProductoCliente 📦
- Producto 🏷️
- Plan 📝

## **Análisis de las clases, atributos y métodos**
### Clatzy
- **Init:** No tiene entradas.
- **Atributos:**
  - `clientes` (privado) (Lista de Cliente)
  - `instructores` (privado) (Lista de Instructor)
  - `cursos` (privado) (Lista de Curso)
  - `planes` (privado) (Lista de Plan)
- **Métodos:**
  - `add_instructor` | params: nombre (str), cedula (str), telefono (str), email (str) | Inicializa un objeto Instructor.
  - `add_curso` | params: id (int), nombre (str), date (date), valor (float raro), instructor (Instructor) | Agrega un curso a la lista de cursos.
  - `get_instructor` | params: index (int) | Retorna un objeto Instructor.
  - `add_plan` | params: nombre (str), date (date), valor (float), valor_maximo_curso (float) | Agrega un objeto Plan a la lista de planes.
  - `add_plan` | params: nombre (str), date (date), valor_maximo_curso (float), valor (float) | Agrega un objeto Plan a la lista de planes.
  - `add_cliente` | params: nombre (str), cedula (str), telefono (str), email (str) | Inicializa un objeto Cliente.
  - `get_cliente` | params: index (int) | Retorna un objeto Cliente.
  - `get_plan` | params: index (int) | Retorna un objeto Plan.
  - `comprar_plan` | params: cliente (Cliente), plan (Plan), date (date) | Asocia un objeto Cliente con un objeto Plan. | el cliente solo puede tener un plan
  - `comprar_curso` | params: cliente (Cliente), plan (Plan), date (date) | Asocia un objeto Cliente con un objeto Plan. | falla si ya tiene el curso
  - `comprar_curso` | params: cliente (Cliente), plan (Plan), date (date), valor (int) | Asocia un objeto Cliente con un objeto Plan.
  - `get_cliente_mayor_ingreso` | params: No contiene.
  - `list_all` | params: No contiene.

### Cliente
- **Init:** nombre (str) (Clase Persona), cedula (str) (Clase Persona), telefono (str) (Clase Persona), email (str) (Clase Persona).
- **Atributos:**
  - `planes` (privado) (Lista de Plan)
  - `productos` (privado) (Lista de Producto)
- **Métodos:**
  - `get_plan` | params: index (int) | Retorna un objeto Plan.
  - `add_producto` | params: producto (Producto)
  - `add_plan` | params: plan (Plan)


### Instructor
- **Init:** nombre (str) (Clase Persona), cedula (str) (Clase Persona), telefono (str) (Clase Persona), email (str) (Clase Persona).
- **Atributos:**
  - `cursos` (privado) (Lista de Curso)
- **Métodos:** 
  - `add_curso` | params: curso (Curso)


### Persona
- **Init:** nombre (str), cedula (str), telefono (str), email (str).
- **Atributos:**
  - `nombre` (protegido) (str)
  - `cedula` (protegido) (str)
  - `telefono` (protegido) (str)
  - `email` (protegido) (str)
- **Métodos:** No tiene métodos.

### Curso
- **Init:** id (int) (Clase Producto), nombre (str) (Clase Producto), date (date) (Clase Producto), valor (float) (Clase Producto), instructor (Instructor) (Clase Producto)
- **Atributos:** Relacion con Instructor
  - `instructores` (privado) (Lista de Instructor)
  - `productos_cliente` (privado) (Lista de ProductoCliente)
- **Métodos:**
  - `add_instructor` | params: instructor (Instructor)
  - `add_producto_cliente` | params: producto_cliente (ProductoCliente)

### PlanCliente
- **Init:** No tiene entradas.
- **Atributos:**
  - `cliente` (privado) (Cliente)
  - `plan` (privado) (Plan)
- **Métodos:** No tiene métodos.
  
### ProductoCliente
- **Init:** No tiene entradas.
- **Atributos:**
  - `estado_aprobado` (privado) (Bool) 
  - `nivel_avance` (privado) (Int)
  - `cliente` (privado) (Cliente)
  - `curso` (privado) (Curso)
- **Métodos:** No tiene métodos.
  
### Producto
- **Init:** No tiene entradas.
- **Atributos:**
  - `id` (protegido) (Int)
  - `nombre` (protegido) (Str)
  - `fecha_inicio` (protegido) (Date)
  - `fecha_fin` (protegido)(Date) 
  - `estado_activo` (protegido) (Bool) 
  - `valor` (protegido) (Float)
- **Métodos:** 
  - `set_estado_activo` | params: estado (Bool)

### Plan
- **Init:**  nombre (str), date (date), valor_maximo_curso (float), valor (float) 
- **Atributos:**
  - `valor_maximo_curso` (private) (Float)
  - `planes` (private) (Lista de Plan)
- **Métodos:** 
  - `add_plan` | params: plan (Plan)

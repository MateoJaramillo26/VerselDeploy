# Django Task Management Application

Este es un proyecto de Django en el cual se explica cómo realizar un despliegue utilizando Vercel y cómo la aplicación funciona completamente con esta plataforma.

## Modelos

### Empleado
Representa un empleado en el sistema.

### Proyecto
Representa un proyecto en el sistema.

### Tarea
Representa una tarea asignada a un empleado dentro de un proyecto.

## Vistas

### `index`
Maneja la generación de un informe de tareas basado en un rango de fechas y el estado de las tareas.

#### Método: `POST`
- Se espera `date_start` y `date_end` como datos del formulario.
- Convierte las fechas de cadenas a objetos `datetime.date`.
- Recupera tareas con estado 'In Progress' y fechas de inicio dentro del rango especificado.
- Calcula la fecha estimada de finalización y el retraso de cada tarea.
- Renderiza las tareas en la plantilla `index.html`.

### `employee`
Maneja la creación y la lista de empleados.

#### Método: `POST`
- Crea un nuevo empleado utilizando `first_name` y `last_name` de los datos del formulario.
- Renderiza la lista de empleados en la plantilla `empleados.html`.

### `project`
Maneja la creación y la lista de proyectos.

#### Método: `POST`
- Crea un nuevo proyecto utilizando `name` de los datos del formulario.
- Renderiza la lista de proyectos en la plantilla `proyectos.html`.

### `task`
Maneja la creación y la lista de tareas.

#### Método: `POST`
- Crea una nueva tarea utilizando `description`, `date_start`, `estimate_time`, `status`, `employee_id` y `project_id` de los datos del formulario.
- Renderiza la lista de tareas, empleados y proyectos en la plantilla `tareas.html`.

### `delete_employee`
Maneja la eliminación de un empleado.

#### Método: `GET`
- Elimina un empleado por `id`.
- Renderiza la lista actualizada de empleados en la plantilla `empleados.html`.

### `delete_project`
Maneja la eliminación de un proyecto.

#### Método: `GET`
- Elimina un proyecto por `id`.
- Renderiza la lista actualizada de proyectos en la plantilla `proyectos.html`.

### `delete_task`
Maneja la eliminación de una tarea.

#### Método: `GET`
- Elimina una tarea por `id`.
- Renderiza la lista actualizada de tareas, empleados y proyectos en la plantilla `tareas.html`.

### `update_task`
Maneja la actualización de una tarea.

#### Método: `POST`
- Actualiza una tarea por `id` utilizando datos del formulario.
- Renderiza la lista actualizada de tareas, empleados y proyectos en la plantilla `tareas.html`.

### `update_employee`
Maneja la actualización de un empleado.

#### Método: `POST`
- Actualiza un empleado por `id` utilizando datos del formulario.
- Renderiza la lista actualizada de empleados en la plantilla `empleados.html`.

### `update_project`
Maneja la actualización de un proyecto.

#### Método: `POST`
- Actualiza un proyecto por `id` utilizando datos del formulario.
- Renderiza la lista actualizada de proyectos en la plantilla `proyectos.html`.

## Plantillas

### `index.html`
Muestra un formulario para ingresar `date_start` y `date_end` para generar informes de tareas y muestra los resultados en formato tabla.

### `empleados.html`
Muestra una lista de empleados y un formulario para agregar nuevos empleados.

### `proyectos.html`
Muestra una lista de proyectos y un formulario para agregar nuevos proyectos.

### `tareas.html`
Muestra una lista de tareas, empleados y proyectos, y un formulario para agregar nuevas tareas.

### `edit_task.html`
Muestra un formulario para editar una tarea existente.

### `edit_employee.html`
Muestra un formulario para editar un empleado existente.

### `edit_project.html`
Muestra un formulario para editar un proyecto existente.

## Uso

1. Clona el repositorio:
    ```sh
    git clone https://github.com/yourusername/task-management-app.git
    cd task-management-app
    ```

2. Crea un entorno virtual e instala las dependencias:
    ```sh
    python -m venv env
    source env/bin/activate  # En Windows, utiliza `env\Scripts\activate`
    pip install -r requirements.txt
    ```

3. Aplica las migraciones de la base de datos:
    ```sh
    python manage.py migrate
    ```

4. Ejecuta el servidor de desarrollo:
    ```sh
    python manage.py runserver
    ```

## Documentación utilizada para hacer el despliegue
- [https://www.youtube.com/watch?v=ZjVzHcXCeMU](https://www.youtube.com/watch?v=ZjVzHcXCeMU)  
- [https://vercel.com/templates/python/django-hello-world](https://vercel.com/templates/python/django-hello-world)

## Video explicativo de cómo se realizó el despliegue
[https://www.youtube.com/watch?v=qUgas5huDkw](https://www.youtube.com/watch?v=qUgas5huDkw)

## Enlace del despliegue
[https://primer-deploy-ruddy.vercel.app/employee/](https://primer-deploy-ruddy.vercel.app/employee/)



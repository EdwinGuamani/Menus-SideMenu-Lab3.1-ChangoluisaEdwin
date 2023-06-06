# Menus-SideMenu-Lab3.1-ChangoluisaEdwin
Cómo definir un menú en XML
Para todos los tipos de menús, Android proporciona un formato XML estándar que permite definir los elementos de menú. En lugar de incorporar un menú en el código de la actividad, debes definir un menú y todos los elementos en un recurso de menú XML. Luego, puedes aumentar el recurso de menú (cargarlo como un objeto Menu) en la actividad o el fragmento.

El uso del recurso de menú es una práctica recomendada por algunos motivos:

Es más fácil visualizar la estructura del menú en XML.
Separa el contenido del menú del código de comportamiento de la aplicación.
Te permite crear configuraciones alternativas del menú para diferentes versiones de plataforma, tamaños de pantalla y otras configuraciones aprovechando el framework de recursos de la app.
Para definir el menú, crea un archivo en formato XML dentro del directorio res/menu/ del proyecto y desarrolla el menú con los siguientes elementos:

<menu>
Define un Menu, que es un contenedor para elementos de menú. Un elemento <menu> debe ser el nodo raíz del archivo y puede tener uno o más elementos <item> y <group>.
<item>
Crea un MenuItem, que representa un único elemento en un menú. Este elemento puede contener un elemento <menu> anidado para crear un submenú.
<group>
Es un contenedor opcional e invisible para elementos <item>. Te permite categorizar los elementos de menú para que compartan propiedades, como el estado de la actividad y la visibilidad. Para obtener más información, consulta la sección Cómo crear grupos del menú.
Aquí presentamos un menú de ejemplo denominado game_menu.xml:


<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:id="@+id/new_game"
          android:icon="@drawable/ic_new_game"
          android:title="@string/new_game"
          android:showAsAction="ifRoom"/>
    <item android:id="@+id/help"
          android:icon="@drawable/ic_help"
          
          android:title="@string/help" />
</menu>
El elemento <item> admite varios atributos que puedes usar para definir la apariencia y el comportamiento de un elemento. Los elementos del menú precedente incluyen estos atributos:

android:id
Es el ID de un recurso que es exclusivo del elemento y permite que la aplicación lo reconozca cuando el usuario lo selecciona.
android:icon
Es la referencia a un elemento de diseño para usar como el ícono del elemento.
android:title
Es la referencia a una string para usar como el título del elemento.
android:showAsAction
Especifica cuándo y cómo el elemento debe aparecer como un elemento de acción en la barra de la app.
Estos son los atributos más importantes que debes usar, pero hay muchos más disponibles. Para obtener información sobre todos los atributos admitidos, consulta el documento Recurso de menú.

Puedes agregar un submenú a un elemento en cualquier menú agregando <menu> como elemento secundario de un <item>. Los submenús son útiles cuando la aplicación tiene muchas funciones que se pueden organizar en temas, como elementos de la barra de menús de una aplicación para PC (Archivo, Editar, Ver, etc.). Por ejemplo:


<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:id="@+id/file"
          android:title="@string/file" >
        <!-- "file" submenu -->
        <menu>
            
            
            <item android:id="@+id/create_new"
                  android:title="@string/create_new" />
            <item android:id="@+id/open"
                  android:title="@string/open" />
        </menu>
    </item>
</menu>

    
    
![10101010](https://github.com/EdwinGuamani/Menus-SideMenu-Lab3.1-ChangoluisaEdwin/assets/133244382/107217c4-8b8c-49a4-be2e-0f449c192f47)

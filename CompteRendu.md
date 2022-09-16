## Exercice 1

1. Les commandes se trouvent dans l'un des dossiers listés dans la variable d'environnement PATH (/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bi)

2. La variable d'environnement HOME contient le répertoire DIR par défaut

3. LANG contient la langue utilisée par le terminal, PWD le répertoire courant, OLDPWD le répertoire mère, SHELL le répertoire du terminal bash

4. `MY_VAR="var"` Crée une variable locale MY_VAR, `echo $MY_VAR` affiche son contenu

5. 

6. `export MY_VAR="var"` crée une variable d'environnement MY_VAR, `printenv MY_VAR` affiche son contenu

7. `export NOM="JOBIN Mathéo"; printenv NOM`

8. `echo "Bonjour à vous, $NOM"`

9. Avec une valeur vide, la variable existe, unset la supprime

10. `echo '$HOME =' "$HOME"` permet d'afficher $HOME = 'chemin vers le répertoire courant'

# Programmation BASH
## Exercice 2
`
    #!/bin/bash

    read -s pass
    if [ $pass = "123456+Aze" ]; then
        echo "Mot de passe correct"
    else 
        echo "Mot de passe incorrect"
    fi
`

## Exercice 3
`
    #!/bin/bash

    function is_number()
    {
        re='^[+-]?[0-9]+([.][0-9]+)?$'

        if ! [[ $1 =~ $re ]] ; then
            return 1
        else
            return 0
        fi
    }

    read -p 'Saisir un nombre réel : ' number

    is_number $number

    if [ $? = 1 ]; then
        echo "Erreur, ce n'est pas un nombre réel"
    fi
`

## Exercice 4
`
    #!/bin/bash

    function exist()
    {
        userExist=$(getent passwd $1)
        if [[ $userExist = "" || $1 = "" ]]; then
            echo -e "\nUtilisation : $0 nom_utilisateur"
        elif ! [ userExist = -z ]; then
            echo -e "\nL'utilisateur $(getent passwd $1) existe "
        fi
    }

    exist $1
`

## Exercice 5

## Exercice 6

## Exercice 7

## Exercice 8
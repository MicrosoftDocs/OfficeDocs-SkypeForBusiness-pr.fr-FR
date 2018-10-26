---
title: Utilisation de l’outil de personnalisation Office (OPO)
TOCTitle: Utilisation de l’outil de personnalisation Office (OPO)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204748(v=OCS.15)
ms:contentKeyID: 49296644
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de l’outil de personnalisation Office (OPO)

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations. Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation. Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau. Quand vous installez Office, le programme d’installation recherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations. Le dossier Updates ne peut être utilisé que pour déployer des mises à jour de logiciels pendant une installation initiale d’Office 2013.

L’outil de personnalisation Office fait partie du programme d’installation et est inclus dans les versions de licence en volume du produit. Exécutez l’Outil de personnalisation Office en tapant `setup.exe /admin` sur la ligne de commande, à la racine du point installation réseau qui contient les fichiers sources d’Office 2013. Par exemple, utilisez la commande suivante :

`\\server\share\Office15\setup.exe /admin`

Les administrateurs utilisent l’outil de personnalisation Office pour créer un fichier .msp de personnalisation de l’installation. Comme dans l’outil de personnalisation Microsoft Office 2010, les administrateurs peuvent personnaliser les domaines suivants :

  - **Installation** Permet de spécifier l’emplacement d’installation par défaut sur le client et le nom d’organisation par défaut, des sources d’installation réseau supplémentaires, la clé du produit, les termes du contrat de licence utilisateur final, le niveau d’affichage, les versions antérieures d’Office à supprimer, les programmes personnalisés à exécuter pendant l’installation, les paramètres de sécurité et les propriétés d’installation.

  - **Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser l’installation des fonctionnalités Office. Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs. Ces derniers peuvent modifier la plupart des paramètres après l’installation.

  - **Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.

  - **Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer des comptes et d’exporter des paramètres, ainsi que de spécifier des groupes d’envoi/réception.

Pour plus d’informations sur l’outil de personnalisation Office, voir [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0x40c).


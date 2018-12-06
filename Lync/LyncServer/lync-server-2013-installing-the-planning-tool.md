---
title: 'Lync Server 2013 : Installation de l’outil de planification'
TOCTitle: Installation de l’outil de planification
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615046(v=OCS.15)
ms:contentKeyID: 53095554
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation de l’outil de planification dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

Avant de commencer à concevoir et à planifier votre infrastructure Lync Server 2013 à l’aide de l’outil de planification Microsoft Lync Server 2013, vous devez d’abord installer l’outil de planification. L’outil de planification n’a pas besoin d’être déployé sur un poste de travail ou un serveur appartenant au domaine ou à l’infrastructure où vous envisagez d’installer Lync Server 2013. Le fichier Lisez-moi qui accompagne l’outil de planification contient des informations importantes sur l’installation et l’utilisation de l’outil. Certaines des informations contenues dans le fichier Lisez-moi sont expliquées ici par souci de clarté.

> [!IMPORTANT]  
> L’outil de planification doit être installé par un utilisateur disposant de droits et d’autorisations d’administration sur l’ordinateur sur lequel l’outil doit être installé.

Les systèmes d’exploitation pris en charge pour l’installation et l’utilisation de l’outil de planification sont les suivants :

  - Windows 8

  - Windows 8.1

  - Windows Server 2012

  - Windows Server 2012 R2

  - Windows 7, édition 32 bits

  - Windows 7, édition 64 bits avec WOW (Windows on Win32)

  - Windows Server 2008 R2 avec WOW

Par ailleurs, l’outil de planification nécessite Microsoft .NET Framework 4.5

Lorsque la configuration requise pré-installation est satisfaite, vous pouvez procéder à l’installation de l’outil de planification.

## Pour installer l’outil de planification

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  À l’aide de l’Explorateur Windows ou d’une fenêtre de commande, recherchez le répertoire dans lequel vous avez téléchargé les fichiers d’installation de l’outil de planification.

3.  Recherchez le fichier LyncPlanningTool.msi. Dans l’Explorateur Windows, double-cliquez sur le fichier. Dans la fenêtre de commande, tapez le nom du fichier, puis appuyez sur **Entrée** pour exécuter le fichier.

4.  Dans la page d’accueil de l’**Assistant Configuration de l’outil de planification Microsoft Lync Server 2013** , cliquez sur **Suivant** .

5.  Passez en revue le **Contrat de Licence Utilisateur Final** , sélectionnez **J’accepte les termes du contrat de licence** si vous choisissez d’accepter les termes d’utilisation contenus dans le contrat de licence, puis cliquez sur **Suivant** .

6.  Choisissez où vous souhaitez installer les fichiers de l’outil de planification. L’emplacement d’installation par défaut est C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool. Si vous souhaitez choisir un autre emplacement, cliquez sur **Modifier** . Dans **Modifier le dossier de destination** , accédez à l’emplacement d’installation des fichiers ou tapez-le directement dans le champ, cliquez sur **OK** , puis sur **Suivant** .

7.  Le programme d’installation est désormais prêt à installer l’outil de planification. Cliquez sur **Installer** pour commencer l’installation.

8.  L’installation débute et la progression s’affiche. Une fois l’installation terminée, cliquez sur **Terminer** .

9.  L’outil de planification est prêt à être utilisé.

## Voir aussi

#### Concepts

[Installation de logiciels facultatifs dans Lync Server 2013](lync-server-2013-installing-optional-software.md)


---
title: 'Lync Server 2013 : utilisation de l’outil de personnalisation Office (OPO)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8943712ff78dcc065a6a75e3756c1c689234eec2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503711"
---
# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Utilisation de l’outil de personnalisation Office (OPO) dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations. Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation. Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau. Quand vous installez Office, le programme d’installation recherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations. Le dossier mises à jour ne peut être utilisé que pour déployer des mises à jour logicielles lors d’une installation initiale d’Office 2013.

L’outil de personnalisation Office fait partie du programme d’installation et est inclus dans les versions de licence en volume du produit. Vous exécutez l’OPO en tapant `setup.exe /admin` sur la ligne de commande à partir de la racine du point d’installation réseau qui contient les fichiers sources Office 2013. Par exemple, utilisez la commande suivante :

`\\server\share\Office15\setup.exe /admin`

Les administrateurs utilisent l’outil de personnalisation Office pour créer un fichier .msp de personnalisation de l’installation. Comme dans l’OPO de Microsoft Office 2010, les administrateurs peuvent personnaliser les domaines suivants :

  - **Programme d’installation** Permet de spécifier l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, les sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage, les versions antérieures d’Office à supprimer, les programmes personnalisés à exécuter pendant l’installation, les paramètres de sécurité et les propriétés d’installation.

  - **Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser l’installation des fonctionnalités Office. Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs. Ces derniers peuvent modifier la plupart des paramètres après l’installation.

  - **Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.

  - **Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer des comptes et d’exporter des paramètres et de spécifier des groupes d’envoi de \\ réception.

Pour plus d’informations sur l’OPO, reportez-vous à <https://go.microsoft.com/fwlink/p/?linkid=267516> .

</div>

<span> </span>

</div>

</div>

</div>


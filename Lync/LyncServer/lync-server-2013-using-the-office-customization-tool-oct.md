---
title: 'Lync Server 2013: utilisation de l’outil de personnalisation Office (OPO)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd9c101b9098f9a5a6ac6088740c067039921b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Utiliser l’outil de personnalisation Office (OPO) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

L’outil de personnalisation Office fait partie du programme d’installation et est recommandé pour de nombreuses personnalisations. Grâce à cet outil, personnalisez Office et enregistrez vos personnalisations dans un fichier .msp de personnalisation de l’installation. Placez ensuite le fichier dans le dossier Updates sur le point d’installation réseau. Lorsque vous installez Office, le programme d’installation cherche un fichier de personnalisation de l’installation dans le dossier Updates et applique les personnalisations. Le dossier mises à jour peut être utilisé uniquement pour déployer des mises à jour logicielles lors d’une installation initiale d’Office 2013.

L’outil de personnalisation Office fait partie du programme d’installation et est inclus dans les versions de licence en volume du produit. Vous exécutez l’outil OCT en `setup.exe /admin` tapant à partir de la ligne de commande à partir de la racine du point d’installation réseau qui contient les fichiers source d’Office 2013. Par exemple, utilisez la commande suivante :

`\\server\share\Office15\setup.exe /admin`

Les administrateurs utilisent l’outil de personnalisation Office pour créer un fichier .msp de personnalisation de l’installation. Comme dans Microsoft Office 2010 OCT, les administrateurs peuvent personnaliser les domaines suivants:

  - **Configuration** Spécifie l’emplacement d’installation par défaut sur le client et le nom de l’organisation par défaut, les sources d’installation réseau supplémentaires, la clé de produit, le contrat de licence utilisateur final, le niveau d’affichage et les versions antérieures d’Office à supprimer, ainsi que les programmes personnalisés à exécuter pendant installation, paramètres de sécurité et propriétés de l’installation.

  - **Fonctionnalités** Permet de configurer les paramètres utilisateur et de personnaliser le mode d’installation des fonctionnalités d’Office. Les administrateurs peuvent utiliser l’outil de personnalisation Office pour spécifier les valeurs par défaut initiales des paramètres de l’application Office pour les utilisateurs. Ces derniers peuvent modifier la plupart des paramètres après l’installation.

  - **Contenu supplémentaire** Permet d’ajouter ou de supprimer des fichiers, d’ajouter ou de supprimer des entrées de Registre et de configurer des raccourcis.

  - **Outlook** Permet de personnaliser le profil Outlook par défaut d’un utilisateur, de spécifier les paramètres Exchange, d’ajouter des comptes, de supprimer les\\comptes et d’exporter des paramètres, et de spécifier les groupes de réception.

Pour plus d’informations sur le PTOM <http://go.microsoft.com/fwlink/p/?linkid=267516>, voir.

</div>

<span> </span>

</div>

</div>

</div>


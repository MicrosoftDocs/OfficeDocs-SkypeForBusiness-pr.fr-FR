---
title: 'Lync Server 2013 : vue d’ensemble de l’environnement hybride Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b39c94b08da65e546fdf3ad01d42ada636ff371d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Vue d’ensemble de l’environnement hybride Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-28_

L’environnement hybride Lync Server 2013 fait référence à un déploiement dans lequel certains utilisateurs sont hébergés sur le serveur Lync Server 2013 sur site et d’autres utilisateurs hébergés sur Lync Online, mais les utilisateurs partagent le même domaine, par exemple user@contoso.com.

<div>

## <a name="about-this-guide"></a>À propos de ce guide

Ce guide décrit les tâches nécessaires pour configurer votre environnement Lync Server 2013 pour l’interopérabilité avec Lync Online, puis pour déplacer les utilisateurs de votre déploiement local vers Lync Online.

</div>

<div>

## <a name="prerequisites"></a>Conditions requises

Les applications et les utilitaires suivants doivent être installés pour effectuer les tâches de configuration d’un déploiement pour un déploiement hybride. Les programmes d’installation de ces fichiers sont inclus sur le support d’installation fourni pour votre déploiement, ainsi que sur les liens inclus dans la liste suivante.

  - [Active Directory Federation Services (ADFS) 2.0](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Outil de synchronisation d’annuaires Microsoft 9,1](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Installer Windows PowerShell pour l’authentification unique avec AD FS](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - L’Assistant de connexion Microsoft Online Services (msoidcli-7.0. msi) est inclus dans le programme d’installation de bureau pour Office 365, qui peut être obtenu à partir de la page de téléchargement liée à partir du centre d’administration Microsoft 365.

</div>

<div>

## <a name="administrator-credentials"></a>Informations d’identification d’administrateur

Lorsque vous êtes invité à fournir vos informations d’identification d’administrateur, utilisez le nom d’utilisateur et le mot de passe pour le compte d’administrateur de votre organisation Office 365. Vous utiliserez également ces informations d’identification lors de la configuration des services AD FS (Active Directory Federation Services) 2,0, de la synchronisation d’annuaires, de la Fédération et du transfert d’utilisateurs vers Lync Online.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Connexion à Lync Online PowerShell

Les administrateurs ont désormais la possibilité d’utiliser Windows PowerShell pour gérer Lync Online et leurs comptes d’utilisateur Lync Online. Pour ce faire, vous devez d’abord télécharger et installer le module Lync Online Connector à partir du centre dehttps://go.microsoft.com/fwlink/?LinkId=294688)téléchargement Microsoft (. Pour plus d’informations sur le téléchargement, l’installation et l’utilisation du module Lync Online Connector et des informations détaillées sur l’utilisation de Windows PowerShell pour gérer Lync Online, voir [Using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>


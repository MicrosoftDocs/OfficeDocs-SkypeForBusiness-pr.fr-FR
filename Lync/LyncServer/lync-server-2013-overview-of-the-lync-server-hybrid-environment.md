---
title: 'Lync Server 2013 : vue d’ensemble de l’environnement hybride Lync Server'
description: 'Lync Server 2013 : vue d’ensemble de l’environnement hybride Lync Server.'
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
ms.openlocfilehash: 95b0ae433dafad349d7ef9b6328e43dbc308579c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552390"
---
# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="b6102-103">Vue d’ensemble de l’environnement hybride Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6102-103">Overview of the Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6102-104">_**Dernière modification de la rubrique :** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="b6102-104">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="b6102-105">L’environnement hybride Lync Server 2013 fait référence à un déploiement dans lequel certains utilisateurs sont hébergés sur le serveur Lync Server 2013 sur site et d’autres utilisateurs hébergés sur Lync Online, mais les utilisateurs partagent le même domaine, par exemple user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b6102-105">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="b6102-106">À propos de ce guide</span><span class="sxs-lookup"><span data-stu-id="b6102-106">About this Guide</span></span>

<span data-ttu-id="b6102-107">Ce guide décrit les tâches nécessaires pour configurer votre environnement Lync Server 2013 pour l’interopérabilité avec Lync Online, puis pour déplacer les utilisateurs de votre déploiement local vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b6102-107">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="b6102-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="b6102-108">Prerequisites</span></span>

<span data-ttu-id="b6102-109">Les applications et les utilitaires suivants doivent être installés pour effectuer les tâches de configuration d’un déploiement pour un déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="b6102-109">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="b6102-110">Les programmes d’installation de ces fichiers sont inclus sur le support d’installation fourni pour votre déploiement, ainsi que sur les liens inclus dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="b6102-110">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="b6102-111">Active Directory Federation Services (ADFS) 2.0</span><span class="sxs-lookup"><span data-stu-id="b6102-111">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="b6102-112">Outil de synchronisation d’annuaires Microsoft 9,1</span><span class="sxs-lookup"><span data-stu-id="b6102-112">Microsoft Directory Synchronization Tool 9.1</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="b6102-113">Installer Windows PowerShell pour l’authentification unique avec AD FS</span><span class="sxs-lookup"><span data-stu-id="b6102-113">Install Windows PowerShell for single sign-on with AD FS</span></span>](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="b6102-114">L’Assistant de connexion Microsoft Online Services (msoidcli-7.0.msi) est inclus dans la configuration de bureau pour Microsoft 365, qui peut être obtenue à partir de la page de téléchargement liée à partir du centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6102-114">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Microsoft 365, which can be obtained from the Downloads page linked to from the Microsoft 365 admin center.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="b6102-115">Informations d’identification d’administrateur</span><span class="sxs-lookup"><span data-stu-id="b6102-115">Administrator Credentials</span></span>

<span data-ttu-id="b6102-116">Lorsque vous êtes invité à fournir vos informations d’identification d’administrateur, utilisez le nom d’utilisateur et le mot de passe du compte d’administrateur pour votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6102-116">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="b6102-117">Vous utiliserez également ces informations d’identification lors de la configuration des services AD FS (Active Directory Federation Services) 2,0, de la synchronisation d’annuaires, de la Fédération et du transfert d’utilisateurs vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b6102-117">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="b6102-118">Connexion à Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6102-118">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="b6102-119">Les administrateurs ont désormais la possibilité d’utiliser Windows PowerShell pour gérer Lync Online et leurs comptes d’utilisateur Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b6102-119">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="b6102-120">Pour ce faire, vous devez d’abord télécharger et installer le module Lync Online Connector à partir du centre de téléchargement Microsoft ( https://go.microsoft.com/fwlink/?LinkId=294688) .</span><span class="sxs-lookup"><span data-stu-id="b6102-120">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="b6102-121">Pour plus d’informations sur le téléchargement, l’installation et l’utilisation du module Lync Online Connector et des informations détaillées sur l’utilisation de Windows PowerShell pour gérer Lync Online, voir [Using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b6102-121">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


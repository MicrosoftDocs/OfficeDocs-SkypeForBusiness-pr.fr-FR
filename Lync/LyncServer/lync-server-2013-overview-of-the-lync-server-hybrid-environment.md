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
ms.openlocfilehash: e32132faee3b52140d20a7f01e6a0bad0e88c620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="410f4-102">Vue d’ensemble de l’environnement hybride Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="410f4-102">Overview of the Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="410f4-103">_**Dernière modification de la rubrique :** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="410f4-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="410f4-104">L’environnement hybride Lync Server 2013 fait référence à un déploiement dans lequel certains utilisateurs sont hébergés sur le serveur Lync Server 2013 sur site et d’autres utilisateurs hébergés sur Lync Online, mais les utilisateurs partagent le même domaine, par exemple user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="410f4-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="410f4-105">À propos de ce guide</span><span class="sxs-lookup"><span data-stu-id="410f4-105">About this Guide</span></span>

<span data-ttu-id="410f4-106">Ce guide décrit les tâches nécessaires pour configurer votre environnement Lync Server 2013 pour l’interopérabilité avec Lync Online, puis pour déplacer les utilisateurs de votre déploiement local vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="410f4-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="410f4-107">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="410f4-107">Prerequisites</span></span>

<span data-ttu-id="410f4-108">Les applications et les utilitaires suivants doivent être installés pour effectuer les tâches de configuration d’un déploiement pour un déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="410f4-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="410f4-109">Les programmes d’installation de ces fichiers sont inclus sur le support d’installation fourni pour votre déploiement, ainsi que sur les liens inclus dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="410f4-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="410f4-110">Active Directory Federation Services (ADFS) 2.0</span><span class="sxs-lookup"><span data-stu-id="410f4-110">Active Directory Federation Services (AD FS) 2.0</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="410f4-111">Outil de synchronisation d’annuaires Microsoft 9,1</span><span class="sxs-lookup"><span data-stu-id="410f4-111">Microsoft Directory Synchronization Tool 9.1</span></span>](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="410f4-112">Installer Windows PowerShell pour l’authentification unique avec AD FS</span><span class="sxs-lookup"><span data-stu-id="410f4-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="410f4-113">L’Assistant de connexion Microsoft Online Services (msoidcli-7.0. msi) est inclus dans le programme d’installation de bureau pour Office 365, qui peut être obtenu à partir de la page de téléchargement liée à partir du portail d’administration d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="410f4-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Office 365, which can be obtained from the Downloads page linked to from the Office 365 Admin portal.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="410f4-114">Informations d’identification d’administrateur</span><span class="sxs-lookup"><span data-stu-id="410f4-114">Administrator Credentials</span></span>

<span data-ttu-id="410f4-115">Lorsque vous êtes invité à fournir vos informations d’identification d’administrateur, utilisez le nom d’utilisateur et le mot de passe pour le compte d’administrateur de votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="410f4-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Office 365 tenant.</span></span> <span data-ttu-id="410f4-116">Vous utiliserez également ces informations d’identification lors de la configuration des services AD FS (Active Directory Federation Services) 2,0, de la synchronisation d’annuaires, de la Fédération et du transfert d’utilisateurs vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="410f4-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="410f4-117">Connexion à Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="410f4-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="410f4-118">Les administrateurs ont désormais la possibilité d’utiliser Windows PowerShell pour gérer Lync Online et leurs comptes d’utilisateur Lync Online.</span><span class="sxs-lookup"><span data-stu-id="410f4-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="410f4-119">Pour ce faire, vous devez d’abord télécharger et installer le module Lync Online Connector à partir du centre dehttp://go.microsoft.com/fwlink/?LinkId=294688)téléchargement Microsoft (.</span><span class="sxs-lookup"><span data-stu-id="410f4-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (http://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="410f4-120">Pour plus d’informations sur le téléchargement, l’installation et l’utilisation du module Lync Online Connector et des informations détaillées sur l’utilisation de Windows PowerShell pour gérer Lync Online, voir [Using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="410f4-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


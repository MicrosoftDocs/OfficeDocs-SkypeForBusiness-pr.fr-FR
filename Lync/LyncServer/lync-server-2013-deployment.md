---
title: 'Lync Server 2013 : déploiement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f77a307b516874449a86f42f84a3053e5f5914
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="5a851-102">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a851-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5a851-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5a851-104">Le déploiement du logiciel de communication Lync Server 2013 inclut la préparation des services de domaine Active Directory (AD FS), le déploiement des serveurs frontaux et des autres composants internes de Lync Server 2013, puis le déploiement d’éventuels rôles et fonctionnalités serveur supplémentaires qui Il est possible que votre organisation exige, comme l’accès des utilisateurs externes et la voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="5a851-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="5a851-105">Cette documentation décrit trois scénarios de déploiement de Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="5a851-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="5a851-106">Nouveau déploiement de Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="5a851-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="5a851-107">Nouveau déploiement de Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5a851-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="5a851-108">Nouveau déploiement de Lync Server 2013 standard édition ou Enterprise Edition dans un déploiement Lync Server 2010 standard édition ou Enterprise Edition existant</span><span class="sxs-lookup"><span data-stu-id="5a851-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="5a851-109">Pour plus d’informations sur le déploiement de Lync Server 2013 dans un environnement Microsoft Office Communications Server 2007 ou Microsoft Office Communications Server 2007 R2, voir la documentation relative à la [migration](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="5a851-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a851-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5a851-110">In This Section</span></span>

  - [<span data-ttu-id="5a851-111">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="5a851-112">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="5a851-113">Déploiement d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="5a851-114">Déploiement de la surveillance dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="5a851-115">Déploiement de l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="5a851-116">Configuration de conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="5a851-117">Planification et déploiement de la vidéo dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="5a851-118">Déploiement de sites de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="5a851-119">Déploiement d’un serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="5a851-120">Déploiement de clients et d’appareils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="5a851-121">Planification et déploiement du magasin de contacts unifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="5a851-122">Gestion des applications d’authentification de serveur à serveur (OAuth) et de partenaire dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="5a851-123">Mise à jour à partir de la version d’évaluation de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="5a851-124">Déploiement du contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="5a851-125">Déploiement de la mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="5a851-126">Configuration de l’intégration à Office Web Apps Server et Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="5a851-127">Configuration de l’intégrité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a851-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


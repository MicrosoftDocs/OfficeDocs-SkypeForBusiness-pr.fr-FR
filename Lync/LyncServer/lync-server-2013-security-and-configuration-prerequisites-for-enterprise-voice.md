---
title: Conditions préalables requises de configuration et de sécurité pour Voix Entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="36a37-102">Conditions préalables à la sécurité et à la configuration pour Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36a37-102">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36a37-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="36a37-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="36a37-104">Vérifiez que votre infrastructure répond à la configuration requise en matière de sécurité, de configuration utilisateur et de matériel spécifique.</span><span class="sxs-lookup"><span data-stu-id="36a37-104">Verify that your infrastructure meets the following security, user configuration, and scenario-specific hardware prerequisites.</span></span>

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a><span data-ttu-id="36a37-105">Droits d’administration et infrastructure de certification</span><span class="sxs-lookup"><span data-stu-id="36a37-105">Administrative Rights and Certificate Infrastructure</span></span>

<span data-ttu-id="36a37-106">Assurez-vous que votre environnement est configuré avec les groupes d’utilisateurs administratifs et l’infrastructure de certification suivants à utiliser au cours du processus de déploiement voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="36a37-106">Be sure that your environment is configured with the following administrative user groups and certificate infrastructure for use during the Enterprise Voice deployment process.</span></span>

  - <span data-ttu-id="36a37-107">Le déploiement d’Enterprise Voice par les administrateurs doit être membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="36a37-107">Administrators deploying Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="36a37-108">Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :</span><span class="sxs-lookup"><span data-stu-id="36a37-108">Administrators performing the configuration tasks must have adequate rights:</span></span>
    
      - <span data-ttu-id="36a37-109">**CsVoiceAdministrator :** ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="36a37-109">**CsVoiceAdministrator:** This administrator role can perform voice configuration tasks, manage voice applications, and assign voice policies to end users.</span></span>
    
      - <span data-ttu-id="36a37-p101">**CsUserAdministrator :** ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="36a37-p101">**CsUserAdministrator:** This administrator role can manage user properties, such as enabling Enterprise Voice for a user. This administrator role can also assign per-user policies, with the exception of the archiving policy; move users; and manage common area phones and analog devices.</span></span>
    
      - <span data-ttu-id="36a37-112">**CsAdministrator :** ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="36a37-112">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="36a37-113">La délégation permet à un plus grand nombre d’administrateurs de participer à votre déploiement Lync Server sans qu’il soit nécessaire d’ouvrir un accès inutile aux ressources.</span><span class="sxs-lookup"><span data-stu-id="36a37-113">Delegation enables more administrators to participate in your Lync Server deployment without opening up unnecessary access to resources.</span></span>

    
    </div>

  - <span data-ttu-id="36a37-114">L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.</span><span class="sxs-lookup"><span data-stu-id="36a37-114">Managed key infrastructure (MKI) is deployed and configured, by using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="36a37-115">Pour plus d’informations sur les exigences relatives aux certificats dans Lync Server, voir <A href="lync-server-2013-certificate-infrastructure-requirements.md">Configuration requise en matière d’infrastructure de certificat pour Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="36a37-115">For details about certificate requirements in Lync Server, see <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="user-configuration"></a><span data-ttu-id="36a37-116">Configuration utilisateur</span><span class="sxs-lookup"><span data-stu-id="36a37-116">User Configuration</span></span>

<span data-ttu-id="36a37-117">Si vous avez localisé le serveur de médiation avec chaque pool frontal ou serveur Standard Edition au cours du déploiement frontal, les paramètres utilisateur nécessaires à l’utilisation d’Enterprise Voice étaient configurés automatiquement lors de l’installation des fichiers pour ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="36a37-117">If you collocated the Mediation Server with each Front End pool or Standard Edition server during Front End deployment, user settings necessary for Enterprise Voice were configured automatically during installation of the files for those server roles.</span></span>

<span data-ttu-id="36a37-118">Si vous venez de déployer la charge de travail voix entreprise pour le moment, avant de commencer le processus de déploiement, spécifiez le numéro de téléphone principal de chaque utilisateur que vous envisagez d’activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="36a37-118">If you are newly deploying the Enterprise Voice workload at this time, before you begin the deployment process, designate a primary phone number for each user who you plan to enable for Enterprise Voice.</span></span> <span data-ttu-id="36a37-119">En tant qu’administrateur, vous devez vous assurer que ce numéro est unique.</span><span class="sxs-lookup"><span data-stu-id="36a37-119">As the administrator, you are responsible for ensuring that this number is unique.</span></span> <span data-ttu-id="36a37-120">Avant l’implémentation, tous les numéros de téléphone principal doivent être normalisés (correctement mis en forme) et copiés sur les propriétés d' **URI de ligne** de chaque utilisateur à l’aide du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36a37-120">Before implementation, all primary phone numbers must be normalized (correctly formatted) and copied to each user’s **Line URI** property using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="36a37-121">Pour obtenir des exemples de numéros de téléphone principaux requis pour le déploiement d’Enterprise Voice, voir les <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et les règles de normalisation dans la section Lync server 2013</A> des <A href="lync-server-2013-dial-plans-and-normalization-rules.md">plans de numérotation et des règles de normalisation dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="36a37-121">For examples of primary phone numbers required for Enterprise Voice deployment, see the <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> section of <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a><span data-ttu-id="36a37-122">Étapes suivantes : installation de fichiers ou configuration de la connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="36a37-122">Next Steps: Install Files or Configure PSTN Connectivity</span></span>

<span data-ttu-id="36a37-123">Après vérification de la configuration logicielle et environnementale requise pour Enterprise Voice, vous pouvez utiliser le contenu suivant :</span><span class="sxs-lookup"><span data-stu-id="36a37-123">After verifying software and environmental prerequisites for Enterprise Voice, you can use the following content to either:</span></span>

  - <span data-ttu-id="36a37-124">Installez le serveur de médiation, comme décrit dans [la rubrique installer les fichiers pour le serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mais uniquement si vous voulez déployer un serveur ou un pool de médiation autonome, car les serveurs de médiation sont installés dans le cadre du processus de déploiement de l’application frontale ou du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="36a37-124">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but only if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

  - <span data-ttu-id="36a37-125">Vous pouvez aussi commencer à configurer des paramètres pour acheminer les appels pour les utilisateurs d’Enterprise Voice, comme décrit dans la rubrique [Configuration des Trunks dans Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="36a37-125">Or, begin configuring settings to route calls for Enterprise Voice users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


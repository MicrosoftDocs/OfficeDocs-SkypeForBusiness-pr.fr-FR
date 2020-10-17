---
title: 'Lync Server 2013 : administration des utilisateurs dans un déploiement hybride'
description: 'Lync Server 2013 : administration des utilisateurs dans un déploiement hybride.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1d7684a9f56eb013574a985ded0313378621c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552990"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="8252d-103">Administration des utilisateurs dans un déploiement hybride de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8252d-103">Administering users in a hybrid Lync Server 2013 deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8252d-104">_**Dernière modification de la rubrique :** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="8252d-104">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="8252d-105">Vous pouvez gérer les paramètres utilisateur et les stratégies pour les utilisateurs migrés vers Lync Online à l’aide des fonctionnalités de gestion des utilisateurs disponibles dans le centre d’administration 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8252d-105">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8252d-106">Vous devez vous connecter à l’aide de votre compte d’administrateur client pour effectuer des tâches d’administration.</span><span class="sxs-lookup"><span data-stu-id="8252d-106">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="8252d-107">Redéplacement des utilisateurs vers l’organisation locale</span><span class="sxs-lookup"><span data-stu-id="8252d-107">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="8252d-108">Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour Lync sur site, puis déplacés d’un déploiement local vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="8252d-108">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="8252d-109">Si vous souhaitez déplacer des utilisateurs qui ont été créés dans Lync Online (et qui n’ont jamais été activés pour Lync dans un déploiement local), reportez-vous à la rubrique <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8252d-109">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="8252d-110">Exécutez les applets de commande suivantes pour déplacer un utilisateur de Lync Online vers Lync local :</span><span class="sxs-lookup"><span data-stu-id="8252d-110">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="8252d-111">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être l’URL du pool où le service de migration hébergée est en cours d’exécution, au format suivant :</span><span class="sxs-lookup"><span data-stu-id="8252d-111">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="8252d-112">Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="8252d-112">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="8252d-113">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du panneau de configuration Lync Online pour votre compte d’organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="8252d-113">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="8252d-114">**Pour déterminer l’URL du service de migration hébergée pour votre organisation Microsoft 365 ou Office 365**</span><span class="sxs-lookup"><span data-stu-id="8252d-114">**To determine the Hosted Migration Service URL for your Microsoft 365 or Office 365 organization**</span></span>

1.  <span data-ttu-id="8252d-115">Connectez-vous à votre organisation en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="8252d-115">Log in to your organization as an administrator.</span></span>

2.  <span data-ttu-id="8252d-116">Ouvrez le **Centre d’administration Lync**.</span><span class="sxs-lookup"><span data-stu-id="8252d-116">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="8252d-117">Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="8252d-117">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="8252d-118">Un exemple d’URL doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8252d-118">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="8252d-119">Remplacez **webdir** dans l’URL par **administrateur**, de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="8252d-119">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="8252d-120">Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="8252d-120">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="8252d-121">L’URL résultante, qui est la valeur de **HostedMigrationOverrideUrl**, doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8252d-121">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>


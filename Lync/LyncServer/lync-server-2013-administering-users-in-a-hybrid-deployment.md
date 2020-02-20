---
title: 'Lync Server 2013 : administration des utilisateurs dans un déploiement hybride'
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
ms.openlocfilehash: 03819bdf387c426c3a0bda5074ad0a36021f68c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="f78d5-102">Administration des utilisateurs dans un déploiement hybride de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f78d5-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f78d5-103">_**Dernière modification de la rubrique :** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="f78d5-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="f78d5-104">Vous pouvez gérer les paramètres utilisateur et les stratégies pour les utilisateurs migrés vers Lync Online à l’aide des fonctionnalités de gestion des utilisateurs disponibles dans le portail en ligne de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="f78d5-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="f78d5-105">Vous devez vous connecter à l’aide de votre compte d’administrateur client pour effectuer des tâches d’administration.</span><span class="sxs-lookup"><span data-stu-id="f78d5-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="f78d5-106">Redéplacement des utilisateurs vers l’organisation locale</span><span class="sxs-lookup"><span data-stu-id="f78d5-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="f78d5-107">Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour Lync sur site, puis déplacés d’un déploiement local vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="f78d5-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="f78d5-108">Si vous souhaitez déplacer des utilisateurs qui ont été créés dans Lync Online (et qui n’ont jamais été activés pour Lync dans un déploiement local), reportez-vous à la rubrique <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f78d5-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="f78d5-109">Exécutez les applets de commande suivantes pour déplacer un utilisateur de Lync Online vers Lync local :</span><span class="sxs-lookup"><span data-stu-id="f78d5-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="f78d5-110">Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être l’URL du pool où le service de migration hébergée est en cours d’exécution, au format suivant :</span><span class="sxs-lookup"><span data-stu-id="f78d5-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="f78d5-111">Nom\<de domaine\>complet du pool https:///HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="f78d5-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="f78d5-112">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="f78d5-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="f78d5-113">**Pour déterminer l’URL du service de migration hébergée pour votre client Office 365**</span><span class="sxs-lookup"><span data-stu-id="f78d5-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="f78d5-114">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f78d5-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="f78d5-115">Ouvrez le **Centre d’administration Lync**.</span><span class="sxs-lookup"><span data-stu-id="f78d5-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="f78d5-116">Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="f78d5-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="f78d5-117">Un exemple d’URL doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f78d5-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="f78d5-118">Remplacez **webdir** dans l’URL par **administrateur**, de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="f78d5-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="f78d5-119">Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="f78d5-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="f78d5-120">L’URL résultante, qui est la valeur de **HostedMigrationOverrideUrl**, doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f78d5-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>


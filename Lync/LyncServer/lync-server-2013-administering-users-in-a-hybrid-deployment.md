---
title: 'Lync Server 2013: administration des utilisateurs dans un déploiement hybride'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd4f53eaa611d130291b1a42c798a8d5589968c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="160ab-102">Administration des utilisateurs dans un déploiement 2013 Lync Server hybride</span><span class="sxs-lookup"><span data-stu-id="160ab-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="160ab-103">_**Dernière modification de la rubrique:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="160ab-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="160ab-104">Vous pouvez gérer les paramètres utilisateur et les stratégies pour les utilisateurs migrés vers Lync Online à l’aide des fonctionnalités de gestion des utilisateurs disponibles sur le portail en ligne Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="160ab-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="160ab-105">Vous devez vous connecter à l’aide d’un compte d’administrateur client pour effectuer des tâches d’administration.</span><span class="sxs-lookup"><span data-stu-id="160ab-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="160ab-106">Replacer les utilisateurs sur le serveur local</span><span class="sxs-lookup"><span data-stu-id="160ab-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="160ab-107">Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour Lync local, puis transférés d’un déploiement local vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="160ab-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="160ab-108">Pour déplacer des utilisateurs qui ont été créés dans Lync Online (et qui ne sont pas encore activés pour Lync dans un déploiement local), voir <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">déplacement des utilisateurs de Lync Online vers Lync local dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="160ab-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="160ab-109">Pour déplacer un utilisateur de Lync Online vers Lync local, exécutez les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="160ab-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```
        $cred=Get-Credential
       ```
    
       ```
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="160ab-110">L’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit correspondre à celle du pool dans lequel le service de migration hébergée est exécuté, au format suivant :</span><span class="sxs-lookup"><span data-stu-id="160ab-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="160ab-111">Nom\<de domaine\>complet (FQDN) du pool https:///HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="160ab-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="160ab-112">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="160ab-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="160ab-113">**Pour déterminer l’URL du service de migration hébergée de votre client Office 365**</span><span class="sxs-lookup"><span data-stu-id="160ab-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="160ab-114">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="160ab-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="160ab-115">Ouvrez le **Centre d’administration Lync**.</span><span class="sxs-lookup"><span data-stu-id="160ab-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="160ab-116">Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresses jusqu’à **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="160ab-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="160ab-117">L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="160ab-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="160ab-118">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="160ab-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="160ab-119">Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="160ab-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="160ab-120">L’URL obtenue, qui est la valeur de **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="160ab-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>


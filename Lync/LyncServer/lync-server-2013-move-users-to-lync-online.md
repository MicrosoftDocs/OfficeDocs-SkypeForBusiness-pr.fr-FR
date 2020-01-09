---
title: 'Lync Server 2013 : déplacer des utilisateurs vers Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6172c526816a3572d6c364b714d5d4e7e5323cac
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="b6b73-102">Déplacer des utilisateurs vers Lync Online dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6b73-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6b73-103">_**Dernière modification de la rubrique :** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="b6b73-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="b6b73-104">Avant de commencer à migrer des utilisateurs vers Lync Online, il est recommandé de sauvegarder les données utilisateur associées aux comptes à déplacer.</span><span class="sxs-lookup"><span data-stu-id="b6b73-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="b6b73-105">Les données utilisateur ne sont pas toutes déplacées avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6b73-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="b6b73-106">Pour plus d’informations, reportez-vous à [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="b6b73-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="b6b73-107">Migration des paramètres utilisateur vers Lync Online</span><span class="sxs-lookup"><span data-stu-id="b6b73-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="b6b73-108">Les paramètres utilisateur sont déplacés en même temps que le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6b73-108">User settings are moved with the user account.</span></span> <span data-ttu-id="b6b73-109">Certains paramètres locaux ne sont pas déplacés avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b6b73-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="b6b73-110">Déplacement d’utilisateurs pilotes vers Lync Online</span><span class="sxs-lookup"><span data-stu-id="b6b73-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="b6b73-111">Avant de commencer à déplacer des utilisateurs vers Lync Online, vous souhaiterez peut-être déplacer quelques utilisateurs du programme pilote pour vérifier que votre environnement est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="b6b73-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="b6b73-112">Vous pouvez ensuite vérifier la fonction et les fonctionnalités de Lync comme prévu avant d’essayer de déplacer d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b6b73-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="b6b73-113">Pour déplacer un utilisateur sur site vers votre client Lync Online, exécutez les applets de commande suivantes dans Lync Server Management Shell, à l’aide des informations d’identification d’administrateur de votre client Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6b73-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="b6b73-114">Remplacez « nomutilisateur@contoso.com » par les informations de l’utilisateur à déplacer.</span><span class="sxs-lookup"><span data-stu-id="b6b73-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="b6b73-115">Le format de l’URL spécifiée pour le paramètre **hostedmigrationoverrideurl doit correspondre** doit être l’URL du pool sur lequel le service de migration hébergé est en cours d’exécution, au format\<suivant :\>nom de domaine complet du pool https:///HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="b6b73-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="b6b73-116">Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6b73-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="b6b73-117">**Pour déterminer l’URL du service de migration hébergée de votre client Office 365**</span><span class="sxs-lookup"><span data-stu-id="b6b73-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="b6b73-118">Connectez-vous à votre client Office 365 en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="b6b73-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="b6b73-119">Ouvrez le **Centre d’administration Lync**.</span><span class="sxs-lookup"><span data-stu-id="b6b73-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="b6b73-120">Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresses jusqu’à **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="b6b73-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="b6b73-121">L’URL doit se présenter comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="b6b73-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="b6b73-122">Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="b6b73-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="b6b73-123">Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="b6b73-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="b6b73-124">L’URL obtenue, qui est la valeur de **HostedMigrationOverrideUrl**, doit se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="b6b73-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="b6b73-125">Déplacement d’utilisateurs vers Lync Online</span><span class="sxs-lookup"><span data-stu-id="b6b73-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="b6b73-126">Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de requête [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) avec le paramètre-Filter pour sélectionner les utilisateurs ayant une propriété spécifique affectée aux comptes d’utilisateurs, par exemple, RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="b6b73-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="b6b73-127">Vous pouvez ensuite canaler les utilisateurs retournés vers l’applet de commande [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , comme le montre l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="b6b73-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="b6b73-128">Vous pouvez également utiliser le paramètre –OU pour extraire tous les utilisateurs de l’unité d’organisation spécifiée, comme indiqué dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="b6b73-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="b6b73-129">Vérifier les fonctionnalités et paramètres utilisateur de Lync Online</span><span class="sxs-lookup"><span data-stu-id="b6b73-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="b6b73-130">Vous pouvez vérifier que le déplacement d’un utilisateur a réussi des deux manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="b6b73-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="b6b73-131">Affichez l’état de l’utilisateur dans le panneau de configuration Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b6b73-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="b6b73-132">L’indicateur visuel des utilisateurs locaux et des utilisateurs en ligne est différent.</span><span class="sxs-lookup"><span data-stu-id="b6b73-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="b6b73-133">Exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b6b73-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>


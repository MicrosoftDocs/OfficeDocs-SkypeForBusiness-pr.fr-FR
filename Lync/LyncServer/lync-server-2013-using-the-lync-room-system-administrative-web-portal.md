---
title: 'Lync Server 2013 : utilisation du portail web d’administration du système de salle Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2369cdde9d14275fddf007b5e073c748ce5a8906
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="8a77b-102">Utilisation du portail web d’administration du système de salle Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a77b-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a77b-103">_**Dernière modification de la rubrique:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="8a77b-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="8a77b-104">Après le déploiement de LRS sur le serveur, vous pouvez vérifier l’état de toutes les pièces LRS en vous connectant au portail Web d’administration LRS à partir d’un navigateur.</span><span class="sxs-lookup"><span data-stu-id="8a77b-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="8a77b-105">Connexion</span><span class="sxs-lookup"><span data-stu-id="8a77b-105">Sign in</span></span>

1.  <span data-ttu-id="8a77b-106">Accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="8a77b-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="8a77b-107">https://\<Fe-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="8a77b-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="8a77b-108">Entrez les informations d’identification pour le compte LRSSupport ou un compte qui a été ajouté au groupe de sécurité LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8a77b-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="8a77b-109">![Écran de connexion du portail d’administration du système de salle Lync] (images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran de connexion du portail d’administration du système de salle Lync")</span><span class="sxs-lookup"><span data-stu-id="8a77b-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="8a77b-110">Page de résumé du portail Web d’administration LRS</span><span class="sxs-lookup"><span data-stu-id="8a77b-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="8a77b-111">La page résumé fournit les informations suivantes pour toutes les salles de LRS déployées sur le serveur:</span><span class="sxs-lookup"><span data-stu-id="8a77b-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="8a77b-112">**Marquez**   le nom personnalisé que l’administrateur accorde à la salle.</span><span class="sxs-lookup"><span data-stu-id="8a77b-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="8a77b-113">Le libellé peut être défini sur le portail en cliquant sur le nom de la salle.</span><span class="sxs-lookup"><span data-stu-id="8a77b-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="8a77b-114">\*\*\*\* État d’intégrité de la salle, qui est dérivée de l’état d’intégrité agrégé de la salle, qui s’affiche dans la section intégrité de la page Paramètres de la salle.   </span><span class="sxs-lookup"><span data-stu-id="8a77b-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="8a77b-115">**Prochaine réunion**   , la date et l’heure auxquelles la prochaine réunion est planifiée.</span><span class="sxs-lookup"><span data-stu-id="8a77b-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="8a77b-116">**LRS version, fabricant, modèle**   ces valeurs sont prédéfinies dans LRS.</span><span class="sxs-lookup"><span data-stu-id="8a77b-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="8a77b-117">Selon la marque, ces champs peuvent rester vides.</span><span class="sxs-lookup"><span data-stu-id="8a77b-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="8a77b-118">**Le dernier rafraîchissement**   affiche la dernière fois que la page Web a été actualisée.</span><span class="sxs-lookup"><span data-stu-id="8a77b-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="8a77b-119">![Affichage de synthèse du portail d’administration du système de salle Lync] (images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Affichage de synthèse du portail d’administration du système de salle Lync")</span><span class="sxs-lookup"><span data-stu-id="8a77b-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="8a77b-120">Informations sur la salle LRS</span><span class="sxs-lookup"><span data-stu-id="8a77b-120">LRS Room Information</span></span>

<span data-ttu-id="8a77b-121">La section infos sur la salle du portail vous permet d’afficher et de configurer des salles LRS individuelles.</span><span class="sxs-lookup"><span data-stu-id="8a77b-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="8a77b-122">Il contient quatre sections: paramètres, détails, résolution des problèmes et santé.</span><span class="sxs-lookup"><span data-stu-id="8a77b-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="8a77b-123">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8a77b-123">Settings</span></span>

<span data-ttu-id="8a77b-124">Dans la section Paramètres, vous pouvez définir le mot de passe, le libellé de la salle et les niveaux de volume par défaut pour la salle.</span><span class="sxs-lookup"><span data-stu-id="8a77b-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="8a77b-125">Si vous configurez ces paramètres, les modifications sont répliquées uniquement après le redémarrage de la console LRS.</span><span class="sxs-lookup"><span data-stu-id="8a77b-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="8a77b-126">Vous ne verrez que les paramètres système pour les systèmes de salle Lync version 15,12 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="8a77b-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="8a77b-127">![Paramètres de la salle du portail d’administration du système de salle Lync] (images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Paramètres de la salle du portail d’administration du système de salle Lync")</span><span class="sxs-lookup"><span data-stu-id="8a77b-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="8a77b-128">Détails</span><span class="sxs-lookup"><span data-stu-id="8a77b-128">Details</span></span>

<span data-ttu-id="8a77b-129">La section Détails fournit une synthèse en lecture seule des paramètres de la salle de LRS, notamment: l’heure de la dernière actualisation; réunion suivante; dernières mises à jour, maintenance et calibrage; paramètres de haut-parleur, micro et sonnerie par défaut; version9.0.2 URI SIP; nombre d’écrans et de détails relatifs à chaque écran; État et activité.</span><span class="sxs-lookup"><span data-stu-id="8a77b-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="8a77b-130">![Affichage détaillé du portail d’administration du système de salle Lync] (images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Affichage détaillé du portail d’administration du système de salle Lync")</span><span class="sxs-lookup"><span data-stu-id="8a77b-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="8a77b-131">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="8a77b-131">Troubleshooting</span></span>

<span data-ttu-id="8a77b-132">La section Dépannage peut être utilisée pour collecter à distance les journaux et les enregistrer à un emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="8a77b-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="8a77b-133">Vous pouvez également redémarrer la console LRS (interface utilisateur d’LRS) ou redémarrer tout le système.</span><span class="sxs-lookup"><span data-stu-id="8a77b-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="8a77b-134">Pour recueillir les journaux, spécifiez un chemin d’accès au dossier au format spécifié et assurez-vous que le dossier possède des autorisations d’écriture fournies au compte d’ordinateur LRS.</span><span class="sxs-lookup"><span data-stu-id="8a77b-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="8a77b-135">Si la taille du journal est trop volumineuse, la collecte peut prendre jusqu’à 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="8a77b-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="8a77b-136">Actualisez la page pour obtenir le dernier statut.</span><span class="sxs-lookup"><span data-stu-id="8a77b-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="8a77b-137">Journalisation de la ![salle du portail d’administration de Lync Room System] Journalisation de la (images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "salle du portail d’administration de Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="8a77b-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="8a77b-138">Intégrité</span><span class="sxs-lookup"><span data-stu-id="8a77b-138">Health</span></span>

<span data-ttu-id="8a77b-139">La section santé donne une indication visuelle de l’état de la connexion du serveur Lync, du périphérique audio, du périphérique vidéo, de l’état de résilience et du périphérique d’écran.</span><span class="sxs-lookup"><span data-stu-id="8a77b-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="8a77b-140">![État d’intégrité de la salle du portail d’administration de Lync Room System] (images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "État d’intégrité de la salle du portail d’administration de Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="8a77b-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="8a77b-141">Remarques supplémentaires concernant le portail Web d’administration</span><span class="sxs-lookup"><span data-stu-id="8a77b-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="8a77b-142">Les modifications apportées aux paramètres ne s’appliquent qu’après le redémarrage du système LRS.</span><span class="sxs-lookup"><span data-stu-id="8a77b-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="8a77b-143">Si le mot de passe du compte LRSApp arrive à expiration, vous ne pourrez pas voir le statut des salles.</span><span class="sxs-lookup"><span data-stu-id="8a77b-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="8a77b-144">Configurez le mot de passe du compte LRSAppuser pour qu’il n’expire jamais, ou veillez à mettre à jour le mot de passe en cas d’expiration proche.</span><span class="sxs-lookup"><span data-stu-id="8a77b-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="8a77b-145">Le portail Web d’administration LRS est uniquement pris en charge pour les déploiements sur site.</span><span class="sxs-lookup"><span data-stu-id="8a77b-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8a77b-146">Forum aux questions</span><span class="sxs-lookup"><span data-stu-id="8a77b-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="8a77b-147">Pourquoi ne puis-je pas me connecter au portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="8a77b-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="8a77b-148">Lorsque vous ouvrez https://localhost/lrsla page de connexion, vous pouvez voir la page de connexion, mais si vous entrez vos informations d’identification, vous ne pourrez pas vous connecter.</span><span class="sxs-lookup"><span data-stu-id="8a77b-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="8a77b-149">Dans ce cas, vous devez ouvrir https://FQDNofFEserver/lrs pour vous connecter au portail Web d’administration.</span><span class="sxs-lookup"><span data-stu-id="8a77b-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="8a77b-150">Si l’ordinateur à partir duquel vous accédez au portail Web d’administration se trouve dans un groupe de travail, «http://» ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="8a77b-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="8a77b-151">Utilisez plutôt «HTTPS».</span><span class="sxs-lookup"><span data-stu-id="8a77b-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="8a77b-152">Pourquoi ne puis-je pas voir LRS dans le portail Web d’administration?</span><span class="sxs-lookup"><span data-stu-id="8a77b-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="8a77b-153">Vérifiez que vous disposez de comptes LRS dans votre déploiement et qu’ils sont créés conformément aux recommandations en matière de déploiement de portail Web LRS d’administration.</span><span class="sxs-lookup"><span data-stu-id="8a77b-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="8a77b-154">Assurez-vous que les comptes LRS sont approvisionnés à l’aide de Enable-CsMeetingRoom, et non d’Enable-CsUser, sur le serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="8a77b-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="8a77b-155">Si vous avez créé des comptes LRS et ne pouvez pas voir les comptes dans le portail Web administratif, recueillez les journaux du serveur à l’aide de l’outil de journalisation de Lync Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact du support technique LRS.</span><span class="sxs-lookup"><span data-stu-id="8a77b-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="8a77b-156">Pourquoi ne puis-je pas voir l’état de LRS dans le portail Web d’administration?</span><span class="sxs-lookup"><span data-stu-id="8a77b-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="8a77b-157">Assurez-vous que le compte d’utilisateur LRSApp est activé pour SIP.</span><span class="sxs-lookup"><span data-stu-id="8a77b-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="8a77b-158">Si vous rencontrez encore des problèmes, collectez le fichier **trace. log** dans le système LRS à partir\\de\\D\\: Tracing LRSAdminLogs, puis envoyez-le à votre contact du support technique LRS.</span><span class="sxs-lookup"><span data-stu-id="8a77b-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


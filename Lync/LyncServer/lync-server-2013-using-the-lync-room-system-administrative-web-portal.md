---
title: 'Lync Server 2013 : utilisation du portail Web d’administration de Lync Room System'
description: 'Lync Server 2013 : utilisation du portail Web d’administration de Lync Room System.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28c29677080bf081eae0fa4227e4cb56ccac697b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579650"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="f53a5-103">Utilisation du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f53a5-103">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f53a5-104">_**Dernière modification de la rubrique :** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="f53a5-104">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="f53a5-105">Une fois que vous avez déployé LRS sur le serveur, vous pouvez vérifier l’état de toutes les salles de LRS en vous connectant au portail Web d’administration de LRS à partir d’un navigateur.</span><span class="sxs-lookup"><span data-stu-id="f53a5-105">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="f53a5-106">Se connecter</span><span class="sxs-lookup"><span data-stu-id="f53a5-106">Sign in</span></span>

1.  <span data-ttu-id="f53a5-107">Accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="f53a5-107">Browse to the following URL:</span></span>
    
    <span data-ttu-id="f53a5-108">https:// \<fe-server\> /LRS</span><span class="sxs-lookup"><span data-stu-id="f53a5-108">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="f53a5-109">Entrez les informations d’identification du compte LRSSupport ou d’un compte qui a été ajouté au groupe de sécurité LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f53a5-109">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="f53a5-110">![Écran de connexion du portail d’administration Lync Room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran de connexion du portail d’administration Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="f53a5-110">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="f53a5-111">Page récapitulative du portail Web d’administration LRS</span><span class="sxs-lookup"><span data-stu-id="f53a5-111">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="f53a5-112">La page de résumé fournit les informations suivantes pour toutes les salles LRS déployées sur le serveur :</span><span class="sxs-lookup"><span data-stu-id="f53a5-112">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="f53a5-113">**Balise**     Nom personnalisé que l’administrateur fournit à la salle.</span><span class="sxs-lookup"><span data-stu-id="f53a5-113">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="f53a5-114">La balise peut être définie dans le portail en cliquant sur le nom de la salle.</span><span class="sxs-lookup"><span data-stu-id="f53a5-114">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="f53a5-115">**Intégrité**     L’état d’intégrité de la salle, qui est dérivé de l’état d’intégrité agrégé de la salle, qui est affiché sous la section intégrité de la page Paramètres de la salle.</span><span class="sxs-lookup"><span data-stu-id="f53a5-115">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="f53a5-116">**Réunion suivante**     Date et heure de la prochaine réunion planifiée.</span><span class="sxs-lookup"><span data-stu-id="f53a5-116">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="f53a5-117">**Version LRS, fabricant, modèle**     Ces valeurs sont prédéfinies dans LRS.</span><span class="sxs-lookup"><span data-stu-id="f53a5-117">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="f53a5-118">En fonction du fabricant, ces champs peuvent rester vides.</span><span class="sxs-lookup"><span data-stu-id="f53a5-118">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="f53a5-119">**Dernière actualisation**     Affiche la date de la dernière actualisation de la page Web.</span><span class="sxs-lookup"><span data-stu-id="f53a5-119">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="f53a5-120">![Affichage de synthèse du portail d’administration de Lync Room System](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Affichage de synthèse du portail d’administration de Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="f53a5-120">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="f53a5-121">Informations sur la salle LRS</span><span class="sxs-lookup"><span data-stu-id="f53a5-121">LRS Room Information</span></span>

<span data-ttu-id="f53a5-122">La section informations sur la salle du portail vous permet d’afficher et de configurer des salles LRS individuelles.</span><span class="sxs-lookup"><span data-stu-id="f53a5-122">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="f53a5-123">Il contient quatre sections : paramètres, détails, résolution des problèmes et intégrité.</span><span class="sxs-lookup"><span data-stu-id="f53a5-123">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="f53a5-124">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f53a5-124">Settings</span></span>

<span data-ttu-id="f53a5-125">Dans la section paramètres, vous pouvez définir le mot de passe, la balise Room et les niveaux de volume par défaut pour la salle.</span><span class="sxs-lookup"><span data-stu-id="f53a5-125">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="f53a5-126">Si vous configurez ces paramètres, les modifications ne sont répliquées qu’une fois que vous avez redémarré la console LRS.</span><span class="sxs-lookup"><span data-stu-id="f53a5-126">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="f53a5-127">Vous verrez uniquement les paramètres de mise à jour du système pour les systèmes de salle Lync qui sont la version 15,12 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="f53a5-127">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="f53a5-128">![Paramètres de la salle du portail d’administration Lync Room System](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Paramètres de la salle du portail d’administration Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="f53a5-128">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="f53a5-129">Détails</span><span class="sxs-lookup"><span data-stu-id="f53a5-129">Details</span></span>

<span data-ttu-id="f53a5-130">La section Détails fournit une synthèse en lecture seule des paramètres de la salle LRS, notamment : l’heure de la dernière actualisation ; réunion suivante ; dernières mises à jour, maintenance et étalonnage ; paramètres de haut-parleur, micro et sonnerie par défaut ; version9.0.2 URI SIP ; nombre d’écrans et détails sur chaque écran ; État et activité.</span><span class="sxs-lookup"><span data-stu-id="f53a5-130">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="f53a5-131">![Affichage détaillé du portail d’administration de Lync Room System](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Affichage détaillé du portail d’administration de Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="f53a5-131">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="f53a5-132">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="f53a5-132">Troubleshooting</span></span>

<span data-ttu-id="f53a5-133">La section Troubleshooting peut être utilisée pour collecter des journaux à distance et les enregistrer à un emplacement spécifié.</span><span class="sxs-lookup"><span data-stu-id="f53a5-133">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="f53a5-134">Vous pouvez également redémarrer la console LRS (interface utilisateur LRS) ou redémarrer l’ensemble du système.</span><span class="sxs-lookup"><span data-stu-id="f53a5-134">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="f53a5-135">Pour collecter les journaux, fournissez un chemin d’accès au dossier au format spécifié et assurez-vous que le dossier dispose des autorisations d’écriture accordées au compte d’ordinateur LRS.</span><span class="sxs-lookup"><span data-stu-id="f53a5-135">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="f53a5-136">Si la taille du journal est trop importante, la collecte des journaux peut prendre jusqu’à 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="f53a5-136">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="f53a5-137">L’actualisation de la page vous donnera le dernier État.</span><span class="sxs-lookup"><span data-stu-id="f53a5-137">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="f53a5-138">![Journalisation de la salle du portail d’administration de Lync Room System](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Journalisation de la salle du portail d’administration de Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="f53a5-138">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="f53a5-139">Intégrité</span><span class="sxs-lookup"><span data-stu-id="f53a5-139">Health</span></span>

<span data-ttu-id="f53a5-140">La section Health fournit une indication visuelle de l’intégrité de la connexion Lync Server, du périphérique audio, du périphérique vidéo, de l’état de résistance et de l’écran.</span><span class="sxs-lookup"><span data-stu-id="f53a5-140">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="f53a5-141">![Intégrité de la salle du portail d’administration Lync Room System](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Intégrité de la salle du portail d’administration Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="f53a5-141">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="f53a5-142">Remarques supplémentaires sur le portail Web d’administration</span><span class="sxs-lookup"><span data-stu-id="f53a5-142">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="f53a5-143">Les modifications de paramètres ne sont appliquées qu’après le redémarrage du système LRS.</span><span class="sxs-lookup"><span data-stu-id="f53a5-143">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="f53a5-144">Si le mot de passe du compte LRSApp expire, vous ne pourrez pas voir l’état des salles.</span><span class="sxs-lookup"><span data-stu-id="f53a5-144">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="f53a5-145">Configurez le mot de passe du compte LRSAppuser de sorte qu’il n’expire jamais, ou veillez à mettre à jour le mot de passe lorsqu’il est proche de son expiration.</span><span class="sxs-lookup"><span data-stu-id="f53a5-145">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="f53a5-146">Le portail Web d’administration LRS est pris en charge uniquement pour les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="f53a5-146">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f53a5-147">Foire aux questions</span><span class="sxs-lookup"><span data-stu-id="f53a5-147">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="f53a5-148">Pourquoi ne puis-je pas me connecter au portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="f53a5-148">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="f53a5-149">Lorsque vous ouvrez https://localhost/lrs , vous pouvez voir la page de connexion, mais lorsque vous tapez vos informations d’identification, vous ne pouvez pas vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f53a5-149">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="f53a5-150">Dans ce cas, vous devez ouvrir https://FQDNofFEserver/lrs la session pour vous connecter au portail Web d’administration.</span><span class="sxs-lookup"><span data-stu-id="f53a5-150">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="f53a5-151">Si l’ordinateur à partir duquel vous accédez au portail Web d’administration se trouve dans un groupe de travail, « http:// » ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="f53a5-151">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="f53a5-152">Utilisez « HTTPS » à la place.</span><span class="sxs-lookup"><span data-stu-id="f53a5-152">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="f53a5-153">Pourquoi ne puis-je pas voir LRS dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="f53a5-153">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="f53a5-154">Assurez-vous que vous disposez de comptes LRS dans votre déploiement et qu’ils sont créés conformément aux recommandations de déploiement du portail Web d’administration LRS.</span><span class="sxs-lookup"><span data-stu-id="f53a5-154">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="f53a5-155">Assurez-vous que les comptes LRS sont mis en service à l’aide de Enable-CsMeetingRoom, et non pas Enable-CsUser, sur le serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="f53a5-155">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="f53a5-156">Si vous avez créé des comptes LRS et que vous ne pouvez pas afficher les comptes dans le portail Web d’administration, collectez les journaux du serveur à l’aide de l’outil de journalisation Lync Server avec le composant **MeetingPortal** sélectionné, puis envoyez-les à votre contact de support LRS.</span><span class="sxs-lookup"><span data-stu-id="f53a5-156">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="f53a5-157">Pourquoi ne puis-je pas voir l’état de LRS dans le portail Web d’administration ?</span><span class="sxs-lookup"><span data-stu-id="f53a5-157">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="f53a5-158">Assurez-vous que le compte d’utilisateur LRSApp est compatible SIP.</span><span class="sxs-lookup"><span data-stu-id="f53a5-158">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="f53a5-159">Si vous rencontrez toujours des problèmes, récupérez le fichier **trace. log** dans le système LRS à partir de D : \\ Tracing \\ LRSAdminLogs \\ , puis envoyez-le à votre contact de support LRS.</span><span class="sxs-lookup"><span data-stu-id="f53a5-159">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: recherche de mises à jour apportées à l’analyseur de meilleures pratiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a52aec0748bb5e96de0b3e6dafae4e05ddf9c15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="999f8-102">Vérification des mises à jour apportées par l’analyseur de meilleures pratiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="999f8-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="999f8-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="999f8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="999f8-104">Lorsque vous démarrez le vérificateur de meilleures pratiques, l’outil vous propose une option pour rechercher les dernières mises à jour apportées à l’outil.</span><span class="sxs-lookup"><span data-stu-id="999f8-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="999f8-105">Si une mise à jour est disponible, vous pouvez télécharger la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="999f8-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="999f8-106">Si vous choisissez de ne pas télécharger les mises à jour, ou si les meilleurs analyseurs ne sont pas en mesure d’accéder à Internet, vous pouvez continuer à utiliser la version déjà installée sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="999f8-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="999f8-107">Si vous avez besoin d’une authentification par proxy pour accéder à Internet, l’analyseur de meilleures pratiques ne peut pas accéder aux nouvelles mises à jour à télécharger.</span><span class="sxs-lookup"><span data-stu-id="999f8-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="999f8-108">Toutefois, vous pouvez télécharger manuellement la dernière version d’RtcBPA. msi à partir du centre de téléchargement <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="999f8-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="999f8-109">Après avoir téléchargé le fichier, vous pouvez le copier sur l’ordinateur sur lequel vous voulez mettre à jour les meilleurs analyseurs et utiliser le fichier. msi pour installer la nouvelle version de l’outil sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="999f8-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="999f8-110">Pour mettre à jour les règles de l’analyseur de meilleures pratiques, vous devez exécuter l’outil en tant qu’administrateur sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="999f8-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="999f8-111">Si vous n’avez pas ouvert de session à l’aide d’un compte membre du groupe administrateurs et des mises à jour sont détectées, fermez l’analyseur de meilleures pratiques, puis utilisez la procédure suivante pour démarrer le programme.</span><span class="sxs-lookup"><span data-stu-id="999f8-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="999f8-112">Pour ouvrir l’outil de recherche de meilleures pratiques en tant qu’administrateur pour rechercher les mises à jour</span><span class="sxs-lookup"><span data-stu-id="999f8-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="999f8-113">Sur un ordinateur sur lequel le système d’analyse des recommandations est installé, cliquez sur **Démarrer**, pointez sur **Microsoft Lync Server 2013**, cliquez avec le bouton droit sur analyseur de **meilleures pratiques**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="999f8-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="999f8-114">Spécifiez les informations d’identification d’un compte membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="999f8-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


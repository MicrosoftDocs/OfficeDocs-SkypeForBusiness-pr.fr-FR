---
title: 'Lync Server 2013 : vérification des mises à jour de Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97dff101a581927ba0d508da45b1f648d1b9908
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520611"
---
# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="c74e6-102">Recherche des mises à jour apportées par Best Practices Analyzer dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74e6-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c74e6-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c74e6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c74e6-104">Lorsque vous démarrez Best Practices Analyzer, l’outil vous offre la possibilité de rechercher les dernières mises à jour de l’outil.</span><span class="sxs-lookup"><span data-stu-id="c74e6-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="c74e6-105">Si une mise à jour est disponible, vous pouvez télécharger la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="c74e6-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="c74e6-106">Si vous choisissez de ne pas télécharger les mises à jour, ou si Best Practices Analyzer ne peut pas accéder à Internet, vous pouvez continuer à utiliser la version qui se trouve déjà sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c74e6-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c74e6-107">Si vous avez besoin d’une authentification proxy pour accéder à Internet, Best Practices Analyzer ne peut pas accéder aux nouvelles mises à jour pour que vous les téléchargiez.</span><span class="sxs-lookup"><span data-stu-id="c74e6-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="c74e6-108">Toutefois, vous pouvez télécharger manuellement la dernière version d' RtcBPA.msi à partir du centre de téléchargement Microsoft à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A> .</span><span class="sxs-lookup"><span data-stu-id="c74e6-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="c74e6-109">Après avoir téléchargé le fichier, vous pouvez le copier sur l’ordinateur sur lequel vous souhaitez mettre à jour Best Practices Analyzer et utiliser le fichier. msi pour installer la nouvelle version de l’outil sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c74e6-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="c74e6-110">Pour mettre à jour les règles de Best Practice Analyzer, vous devez exécuter l’outil en tant qu’administrateur sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="c74e6-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="c74e6-111">Si vous n’avez pas ouvert de session à l’aide d’un compte membre du groupe administrateurs et que des mises à jour sont détectées, fermez Best Practices Analyzer, puis utilisez la procédure suivante pour démarrer le programme.</span><span class="sxs-lookup"><span data-stu-id="c74e6-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="c74e6-112">Pour ouvrir Best Practices Analyzer en tant qu’administrateur pour vérifier les mises à jour</span><span class="sxs-lookup"><span data-stu-id="c74e6-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="c74e6-113">Sur un ordinateur sur lequel Best Practices Analyzer est installé, cliquez sur **Démarrer**, pointez sur **Microsoft Lync Server 2013**, cliquez avec le bouton droit sur **Best Practices Analyzer**, puis cliquez sur **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="c74e6-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="c74e6-114">Spécifiez les informations d’identification d’un compte membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="c74e6-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


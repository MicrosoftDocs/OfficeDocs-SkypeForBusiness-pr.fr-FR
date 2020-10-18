---
title: 'Lync Server 2013 : utilisation d’une journalisation enrichie pour les transactions synthétiques'
description: 'Lync Server 2013 : utilisation d’une journalisation enrichie pour les transactions synthétiques.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fd984386985bced64265ebedfd57c56a84a4443
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580300"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="14c1e-103">Utilisation d’une journalisation enrichie pour les transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14c1e-103">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14c1e-104">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="14c1e-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="14c1e-105">Les transactions synthétiques (introduites dans Microsoft Lync Server 2010) permettent aux administrateurs de vérifier que les utilisateurs peuvent effectuer correctement des tâches courantes telles qu’ouvrir une session sur le système, échanger des messages instantanés ou appeler un téléphone situé sur le réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="14c1e-105">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="14c1e-106">Ces tests (qui sont empaquetés sous la forme d’un ensemble d’applets de commande Windows PowerShell de Lync Server) peuvent être effectués manuellement par un administrateur ou être exécutés automatiquement par une application telle que System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="14c1e-106">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="14c1e-107">Dans Lync Server 2010, les transactions synthétiques se sont révélées extrêmement utiles pour aider les administrateurs à identifier les problèmes liés au système.</span><span class="sxs-lookup"><span data-stu-id="14c1e-107">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="14c1e-108">Par exemple, l’applet de commande **test-CsRegistration** pourrait alerter les administrateurs du fait que certains utilisateurs ont des difficultés à s’inscrire auprès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14c1e-108">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="14c1e-109">Toutefois, les transactions synthétiques étaient quelque peu moins utiles pour aider les administrateurs à déterminer pourquoi ces utilisateurs ont des difficultés à s’inscrire auprès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14c1e-109">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="14c1e-110">Cela est dû au fait que les transactions synthétiques n’ont pas fourni d’informations de journalisation détaillées pouvant aider les administrateurs à résoudre les problèmes liés à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14c1e-110">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="14c1e-111">Au mieux, la sortie détaillée d’une transaction synthétique fournissait des informations pas à pas susceptibles de permettre à un administrateur d’émettre des hypothèses éclairées sur l’origine du problème.</span><span class="sxs-lookup"><span data-stu-id="14c1e-111">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="14c1e-112">Dans Microsoft Lync Server 2013, les transactions synthétiques ont été remaniées afin de fournir une journalisation enrichie.</span><span class="sxs-lookup"><span data-stu-id="14c1e-112">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="14c1e-113">« Journalisation enrichie » signifie que, pour chaque activité qu’une transaction synthétique s’exécute, des informations telles que celles-ci seront enregistrées :</span><span class="sxs-lookup"><span data-stu-id="14c1e-113">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="14c1e-114">L’heure de début de l’activité</span><span class="sxs-lookup"><span data-stu-id="14c1e-114">The time that the activity started</span></span>

  - <span data-ttu-id="14c1e-115">L’heure de fin de l’activité</span><span class="sxs-lookup"><span data-stu-id="14c1e-115">The time that the activity finished</span></span>

  - <span data-ttu-id="14c1e-116">Action effectuée (par exemple, la création, la participation ou la fermeture d’une conférence ; connexion à Lync Server ; envoi d’un message instantané, etc.)</span><span class="sxs-lookup"><span data-stu-id="14c1e-116">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="14c1e-117">Les messages informatifs, détaillés, d’avertissement ou d’erreur générés pendant l’exécution de l’activité</span><span class="sxs-lookup"><span data-stu-id="14c1e-117">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="14c1e-118">Les messages d’inscription SIP</span><span class="sxs-lookup"><span data-stu-id="14c1e-118">SIP registration messages</span></span>

  - <span data-ttu-id="14c1e-119">Les enregistrements d’exception ou codes de diagnostic générés pendant l’exécution de l’activité</span><span class="sxs-lookup"><span data-stu-id="14c1e-119">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="14c1e-120">Le résultat net suite à l’exécution de l’activité</span><span class="sxs-lookup"><span data-stu-id="14c1e-120">The net result of running the activity</span></span>

<span data-ttu-id="14c1e-121">Ces informations sont automatiquement générées à chaque exécution d’une transaction synthétique.</span><span class="sxs-lookup"><span data-stu-id="14c1e-121">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="14c1e-122">Toutefois, elles ne sont pas automatiquement affichées ou enregistrées dans un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="14c1e-122">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="14c1e-123">Au lieu de cela, les administrateurs qui exécutent manuellement une transaction synthétique peuvent utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle les informations seront stockées.</span><span class="sxs-lookup"><span data-stu-id="14c1e-123">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="14c1e-124">À partir de là, les administrateurs peuvent utiliser deux méthodes pour enregistrer et/ou afficher le journal enrichi au format XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="14c1e-124">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="14c1e-125">Par exemple, les administrateurs de Lync Server 2010 peuvent exécuter l’applet de commande **test-CsRegistration** à l’aide d’une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="14c1e-125">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="14c1e-126">Ils ont la possibilité d’inclure le paramètre OutLoggerVariable suivi d’un nom de variable de leur choix :</span><span class="sxs-lookup"><span data-stu-id="14c1e-126">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="14c1e-p105">Ne faites pas précéder le nom de variable du caractère $. Utilisez un nom de variable comme RegistrationTest et non $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="14c1e-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="14c1e-129">La commande précédente permet d’obtenir du contenu de type :</span><span class="sxs-lookup"><span data-stu-id="14c1e-129">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="14c1e-p106">Toutefois, il est possible d’obtenir des informations bien plus détaillées pour cette panne que le simple message d’erreur indiqué plus haut. Utilisez une commande de ce type pour enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML et pouvoir y accéder :</span><span class="sxs-lookup"><span data-stu-id="14c1e-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="14c1e-132">Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :</span><span class="sxs-lookup"><span data-stu-id="14c1e-132">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="14c1e-133">Ces fichiers peuvent ensuite être affichés à l’aide d’Internet Explorer, de Visual Studio ou de toute autre application capable d’ouvrir des fichiers HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="14c1e-133">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="14c1e-134">Les transactions synthétiques exécutées à l’intérieur de System Center Operations Manager génèrent automatiquement ces fichiers journaux pour les échecs.</span><span class="sxs-lookup"><span data-stu-id="14c1e-134">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="14c1e-135">Toutefois, ces journaux ne seront pas générés si l’exécution échoue avant que Windows PowerShell ne puisse charger et exécuter la transaction synthétique.</span><span class="sxs-lookup"><span data-stu-id="14c1e-135">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="14c1e-136">Par défaut, Lync Server 2013 enregistre les fichiers journaux dans un dossier qui n’est pas partagé.</span><span class="sxs-lookup"><span data-stu-id="14c1e-136">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="14c1e-137">Pour faciliter l’accès à ces journaux, vous devez partager ce dossier (par exemple, \\ \\ ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="14c1e-137">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>


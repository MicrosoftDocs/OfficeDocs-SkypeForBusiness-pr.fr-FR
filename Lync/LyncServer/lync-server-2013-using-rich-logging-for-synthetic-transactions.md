---
title: 'Lync Server 2013 : utilisation de la journalisation détaillée pour les transactions synthétiques'
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
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="b619a-102">Utilisation de la journalisation détaillée pour les transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b619a-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b619a-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b619a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b619a-104">Les transactions synthétiques (introduites dans Microsoft Lync Server 2010) permettent aux administrateurs de vérifier que l’utilisateur est en mesure d’effectuer des tâches courantes telles que la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone sur le réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="b619a-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="b619a-105">Ces tests (qui sont empaquetés sous la forme d’un ensemble de cmdlets Windows PowerShell Lync Server) peuvent être dirigés manuellement par un administrateur, ou s’ils peuvent être exécutés automatiquement par une application telle que System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b619a-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="b619a-106">Dans Lync Server 2010, les transactions synthétiques ont été particulièrement utiles pour aider les administrateurs à identifier les problèmes du système.</span><span class="sxs-lookup"><span data-stu-id="b619a-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="b619a-107">Par exemple, l’applet de **contrôle test-CsRegistration** peut signaler aux administrateurs que certains utilisateurs éprouvent des difficultés à s’inscrire auprès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b619a-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="b619a-108">Toutefois, les transactions synthétiques étaient légèrement moins utiles pour permettre aux administrateurs de déterminer pourquoi ces utilisateurs éprouvent des difficultés à s’inscrire auprès de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b619a-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="b619a-109">Ce problème est dû au fait que les transactions synthétiques n’ont pas fourni d’informations de journalisation détaillées susceptibles d’aider les administrateurs à résoudre les problèmes avec Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b619a-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="b619a-110">Dans la mesure du possible, la sortie détaillée d’une transaction synthétique vous a fourni des informations détaillées qui pourraient permettre à un administrateur de découvrir à quel point un problème est susceptible de se produire.</span><span class="sxs-lookup"><span data-stu-id="b619a-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="b619a-111">Dans Microsoft Lync Server 2013, les transactions synthétiques ont été repensées pour fournir une journalisation enrichie.</span><span class="sxs-lookup"><span data-stu-id="b619a-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="b619a-112">« La journalisation enrichie » signifie qu’à chaque activité qu’une transaction synthétique s’engage, des informations telles que celles-ci seront enregistrées :</span><span class="sxs-lookup"><span data-stu-id="b619a-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="b619a-113">Heure de début de l’activité</span><span class="sxs-lookup"><span data-stu-id="b619a-113">The time that the activity started</span></span>

  - <span data-ttu-id="b619a-114">Heure de fin de l’activité</span><span class="sxs-lookup"><span data-stu-id="b619a-114">The time that the activity finished</span></span>

  - <span data-ttu-id="b619a-115">Action exécutée (par exemple, création, participation ou départ d’une conférence ; connexion à Lync Server ; envoi d’un message instantané ; etc.)</span><span class="sxs-lookup"><span data-stu-id="b619a-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="b619a-116">Les messages informatifs, détaillés, d’avertissement ou d’erreur générés pendant l’exécution de l’activité.</span><span class="sxs-lookup"><span data-stu-id="b619a-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="b619a-117">Messages d’enregistrement SIP</span><span class="sxs-lookup"><span data-stu-id="b619a-117">SIP registration messages</span></span>

  - <span data-ttu-id="b619a-118">Enregistrements d’exceptions ou codes de diagnostic générés lors de l’exécution de l’activité</span><span class="sxs-lookup"><span data-stu-id="b619a-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="b619a-119">Résultat net de l’exécution de l’activité</span><span class="sxs-lookup"><span data-stu-id="b619a-119">The net result of running the activity</span></span>

<span data-ttu-id="b619a-120">Ces informations sont générées automatiquement chaque fois qu’une transaction synthétique est exécutée.</span><span class="sxs-lookup"><span data-stu-id="b619a-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="b619a-121">Toutefois, les informations ne sont pas affichées ou enregistrées automatiquement dans un fichier journal.</span><span class="sxs-lookup"><span data-stu-id="b619a-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="b619a-122">À la place, les administrateurs exécutant une transaction synthétique manuellement peuvent utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle les informations seront stockées.</span><span class="sxs-lookup"><span data-stu-id="b619a-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="b619a-123">À partir de là, les administrateurs peuvent utiliser une paire de méthodes qui leur permettent d’enregistrer et/ou d’afficher le journal enrichi au format XML ou HTML.</span><span class="sxs-lookup"><span data-stu-id="b619a-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="b619a-124">Par exemple, les administrateurs de Lync Server 2010 peuvent exécuter l’applet de commande **test-CsRegistration** à l’aide d’une commande similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b619a-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="b619a-125">Les administrateurs ont la possibilité d’inclure le paramètre OutLoggerVariable, suivi du nom de la variable de leur choix :</span><span class="sxs-lookup"><span data-stu-id="b619a-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="b619a-126">Ne faites pas précéder le nom de la variable du caractère $.</span><span class="sxs-lookup"><span data-stu-id="b619a-126">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="b619a-127">Utilisez un nom de variable tel que RegistrationTest et non $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="b619a-127">Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="b619a-128">La commande précédente génère du contenu similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b619a-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="b619a-129">Toutefois, des informations plus détaillées sont disponibles pour cet échec que le message d’erreur ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="b619a-129">However, much more detailed information is available for this failure than just the error message shown above.</span></span> <span data-ttu-id="b619a-130">Pour accéder à ces informations au format HTML, utilisez une commande similaire à celle-ci afin d’enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML :</span><span class="sxs-lookup"><span data-stu-id="b619a-130">To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="b619a-131">Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :</span><span class="sxs-lookup"><span data-stu-id="b619a-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="b619a-132">Ces fichiers peuvent être affichés à l’aide d’Internet Explorer, Visual Studio ou de toute autre application capable d’ouvrir des fichiers HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="b619a-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="b619a-133">Les transactions synthétiques exécutées à partir de System Center Operations Manager génèrent automatiquement ces fichiers journaux pour les échecs.</span><span class="sxs-lookup"><span data-stu-id="b619a-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="b619a-134">Toutefois, ces journaux ne seront pas générés en cas d’échec de l’exécution avant que Windows PowerShell puisse charger et exécuter la transaction synthétique.</span><span class="sxs-lookup"><span data-stu-id="b619a-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="b619a-135">Par défaut, Lync Server 2013 enregistre les fichiers journaux dans un dossier qui n’est pas partagé.</span><span class="sxs-lookup"><span data-stu-id="b619a-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="b619a-136">Pour rendre ces journaux facilement accessibles, vous devez partager ce dossier (par exemple, \\ \\ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="b619a-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>


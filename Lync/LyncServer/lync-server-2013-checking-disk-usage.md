---
title: 'Lync Server 2013 : vérification de l’utilisation du disque'
description: 'Lync Server 2013 : vérification de l’utilisation du disque.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7eddde772d156f0a416dab381efe1ab33ee202f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571000"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="7b2d2-103">Vérification de l’utilisation du disque dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b2d2-103">Checking disk usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b2d2-104">_**Dernière modification de la rubrique :** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="7b2d2-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="7b2d2-105">Les disques durs sont un composant important du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-105">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="7b2d2-106">Sans volume de disque libre suffisant, ni le système d’exploitation ni les bases de données Lync Server 2013 ne fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-106">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="7b2d2-107">Vous devez surveiller quotidiennement les statistiques de la base de données principale Lync Server 2013 afin de vous assurer que les serveurs ne manquent pas d’espace disque et de se préparer à ajouter des ressources de stockage selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-107">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="7b2d2-108">Outre l’espace sur les disques hébergeant le système d’exploitation, les fichiers de programme, les bases de données et les journaux de transaction (Lync Server 2013 back end), vous devez également surveiller l’utilisation du système de fichiers qui inclut l’espace disque pour les partages de fichiers qui contiennent les données importantes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b2d2-108">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="7b2d2-109">Contenu de la réunion</span><span class="sxs-lookup"><span data-stu-id="7b2d2-109">Meeting content</span></span>

  - <span data-ttu-id="7b2d2-110">Métadonnées de contenu de réunion</span><span class="sxs-lookup"><span data-stu-id="7b2d2-110">Meeting content metadata</span></span>

  - <span data-ttu-id="7b2d2-111">Journaux de conformité des réunions</span><span class="sxs-lookup"><span data-stu-id="7b2d2-111">Meeting compliance logs</span></span>

  - <span data-ttu-id="7b2d2-112">Fichiers de données d’application (utilisés en interne par le composant du serveur d’applications)</span><span class="sxs-lookup"><span data-stu-id="7b2d2-112">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="7b2d2-113">Dossiers de service Web et de conformité du serveur de conversation de groupe (pour stocker les fichiers téléchargés vers le service Web de conversation de groupe)</span><span class="sxs-lookup"><span data-stu-id="7b2d2-113">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="7b2d2-114">Fichiers XML de conformité de conversation de groupe (qui contiennent des enregistrements de conformité de conversation de groupe)</span><span class="sxs-lookup"><span data-stu-id="7b2d2-114">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="7b2d2-115">Mettre à jour les fichiers (pour le service de mise à jour des périphériques)</span><span class="sxs-lookup"><span data-stu-id="7b2d2-115">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="7b2d2-116">Fichiers du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="7b2d2-116">Address Book files</span></span>

<span data-ttu-id="7b2d2-117">Lync Server 2013 a besoin d’espace disque pour stocker ses bases de données et ses journaux de transaction en plus des fichiers figurant dans la zone de partage de fichiers précédemment indiquée.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-117">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="7b2d2-118">Vous devez surveiller régulièrement l’espace disque afin de vous assurer que le déploiement de Lync Server 2013 n’est pas affecté par des ressources de stockage insuffisantes.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-118">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="7b2d2-119">Comparez et gérez les informations statistiques relatives à l’espace disque disponible sur chaque volume Lync Server 2013 et la croissance attendue des bases de données et des fichiers journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-119">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="7b2d2-120">Cela permet de planifier la capacité et d’ajouter de l’espace de stockage lorsque les ressources de stockage sont requises.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-120">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="7b2d2-121">Pour tenir compte des situations de dépannage et de récupération d’urgence, nous vous recommandons d’utiliser un espace de volume disponible égal ou supérieur à 110% de la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-121">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="7b2d2-122">Vous pouvez vérifier l'espace disque disponible en utilisant les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b2d2-122">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="7b2d2-123">**System Center Operations Manager**     System Center Operations Manager peut être utilisé pour avertir les administrateurs lorsque l’espace de volume est limité.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-123">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="7b2d2-124">**Exécution d’un script**     Surveillez l’espace disque en exécutant un script qui vous envoie un message si l’espace disponible sur le disque tombe en dessous de 20%.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-124">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="7b2d2-125">Vous trouverez un exemple de script sur le centre de scripts Microsoft sur TechNet : [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="7b2d2-125">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="7b2d2-126">**Explorateur Windows**     Utilisez l’Explorateur Windows pour vérifier l’espace disque sur les volumes qui stockent les journaux et les bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b2d2-126">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


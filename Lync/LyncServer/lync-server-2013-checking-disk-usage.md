---
title: 'Lync Server 2013 : vérification de l’utilisation du disque'
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
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="baf6e-102">Vérification de l’utilisation du disque dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="baf6e-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baf6e-103">_**Dernière modification de la rubrique :** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="baf6e-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="baf6e-104">Les disques durs sont une composante importante du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="baf6e-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="baf6e-105">Le système d’exploitation et les bases de données 2013 de Lync Server peuvent fonctionner correctement sans le volume de disque libre suffisant.</span><span class="sxs-lookup"><span data-stu-id="baf6e-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="baf6e-106">Vous devez surveiller quotidiennement les statistiques de la base de données principale de Lync Server 2013 pour vous assurer que les serveurs ne manquent pas d’espace disque et préparer l’ajout de ressources de stockage selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="baf6e-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="baf6e-107">Outre le contrôle de l’espace sur les disques hébergeant le système d’exploitation, les fichiers de programme, la base de données et les journaux de transactions (serveur principal Lync Server 2013), vous devez également surveiller l’utilisation du système de fichiers qui inclut l’espace disque pour les partages de fichiers qui contiennent les éléments suivants : données</span><span class="sxs-lookup"><span data-stu-id="baf6e-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="baf6e-108">Contenu de la réunion</span><span class="sxs-lookup"><span data-stu-id="baf6e-108">Meeting content</span></span>

  - <span data-ttu-id="baf6e-109">Métadonnées de contenu de réunion</span><span class="sxs-lookup"><span data-stu-id="baf6e-109">Meeting content metadata</span></span>

  - <span data-ttu-id="baf6e-110">Journaux de conformité des réunions</span><span class="sxs-lookup"><span data-stu-id="baf6e-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="baf6e-111">Fichiers de données d’application (utilisés en interne par le composant Application Server)</span><span class="sxs-lookup"><span data-stu-id="baf6e-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="baf6e-112">Service Web de groupe de discussion et dossiers de conformité (pour le stockage des fichiers téléchargés vers le service Web de discussion de groupe)</span><span class="sxs-lookup"><span data-stu-id="baf6e-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="baf6e-113">Fichiers XML de mise en conformité des conversations de groupe (qui contiennent les enregistrements de conformité des conversations de groupe)</span><span class="sxs-lookup"><span data-stu-id="baf6e-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="baf6e-114">Fichiers de mise à jour (pour le service de mise à jour d’appareils)</span><span class="sxs-lookup"><span data-stu-id="baf6e-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="baf6e-115">Fichiers du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="baf6e-115">Address Book files</span></span>

<span data-ttu-id="baf6e-116">Lync Server 2013 a besoin d’espace disque dur pour stocker ses bases de données et journaux de transactions en plus des fichiers figurant dans les partages de fichiers figurant précédemment dans la liste.</span><span class="sxs-lookup"><span data-stu-id="baf6e-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="baf6e-117">Vous devez surveiller régulièrement l’espace disque pour vous assurer que le déploiement de Lync Server 2013 n’est pas affecté en raison de ressources de stockage insuffisantes.</span><span class="sxs-lookup"><span data-stu-id="baf6e-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="baf6e-118">Comparer et tenir à jour des informations statistiques sur l’espace disque disponible sur chaque volume Lync Server 2013 et croissance attendue des bases de données et des fichiers du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="baf6e-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="baf6e-119">Cela favorise la planification de la capacité et l’ajout d’espace de stockage lorsque les ressources de stockage sont nécessaires.</span><span class="sxs-lookup"><span data-stu-id="baf6e-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="baf6e-120">Pour prendre en charge la résolution des problèmes et les situations de reprise après sinistre, nous vous recommandons d’utiliser une quantité d’espace libre disponible égale ou supérieure à 110% de la taille de la base de données.</span><span class="sxs-lookup"><span data-stu-id="baf6e-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="baf6e-121">Vous pouvez vérifier l’espace disque disponible en utilisant les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="baf6e-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="baf6e-122">**System Center**   Operations Manager System Center Operations Manager peut être utilisé pour avertir les administrateurs lorsque l’espace disque est limité.</span><span class="sxs-lookup"><span data-stu-id="baf6e-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="baf6e-123">**L’exécution d’un script**   du moniteur de script en exécutant un script qui vous envoie un message si l’espace disponible sur le disque dur est inférieur à 20%.</span><span class="sxs-lookup"><span data-stu-id="baf6e-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="baf6e-124">Vous trouverez un exemple de script sur le centre de scripts Microsoft sur TechNet et examinez les éléments suivants :[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="baf6e-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="baf6e-125">**L’Explorateur**   Windows permet de vérifier l’espace disque sur les volumes qui stockent les journaux et bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="baf6e-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>


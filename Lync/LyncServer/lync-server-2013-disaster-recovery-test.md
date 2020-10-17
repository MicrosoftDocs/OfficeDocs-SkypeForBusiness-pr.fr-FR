---
title: 'Lync Server 2013 : test de récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2d36ec6ad1afb8c41c7c5f614e90e03ce4d9282
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528951"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="c287f-102">Test de récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c287f-102">Disaster recovery test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c287f-103">_**Dernière modification de la rubrique :** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="c287f-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="c287f-104">Effectuez une récupération système pour un serveur de pool Lync Server 2013 afin de tester votre processus de récupération d’urgence documenté.</span><span class="sxs-lookup"><span data-stu-id="c287f-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="c287f-105">Ce test simule une défaillance matérielle complète pour un serveur, et vous aide à garantir que les ressources, les plans et les données sont disponibles pour la récupération.</span><span class="sxs-lookup"><span data-stu-id="c287f-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="c287f-106">Essayez de faire pivoter la sélection du test chaque mois afin que votre organisation teste l’échec à chaque fois d’un autre serveur ou d’un autre équipement.</span><span class="sxs-lookup"><span data-stu-id="c287f-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="c287f-107">Notez que le calendrier par lequel les organisations effectuent des tests de récupération d’urgence varient.</span><span class="sxs-lookup"><span data-stu-id="c287f-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="c287f-108">Il est très important que les tests de récupération d’urgence ne soient pas ignorés ou négligés.</span><span class="sxs-lookup"><span data-stu-id="c287f-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="c287f-109">Exportez votre topologie, vos stratégies et vos paramètres de configuration Lync Server 2013 vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="c287f-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="c287f-110">Entre autres, ce fichier peut ensuite être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème est à l’issue d’une perte de données.</span><span class="sxs-lookup"><span data-stu-id="c287f-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="c287f-111">Importez votre topologie Lync Server 2013, vos stratégies et vos paramètres de configuration dans le magasin central de gestion ou sur l’ordinateur local comme illustré dans les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c287f-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="c287f-112">Pour sauvegarder les données de production Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="c287f-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="c287f-113">Sauvegardez les bases de données RTC et LCSLog à l’aide du processus de sauvegarde SQL Server standard pour vider la base de données vers un fichier ou un périphérique de vidage de bande.</span><span class="sxs-lookup"><span data-stu-id="c287f-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="c287f-114">Utilisez une application de sauvegarde tierce pour sauvegarder les données dans un fichier ou sur une bande.</span><span class="sxs-lookup"><span data-stu-id="c287f-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="c287f-115">Utilisez l’applet de commande Export-CsUserData pour créer une exportation XML de l’ensemble de la base de données RTC.</span><span class="sxs-lookup"><span data-stu-id="c287f-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="c287f-116">Utilisez la sauvegarde du système de fichiers ou une tierce partie pour sauvegarder le contenu et les journaux de conformité des réunions.</span><span class="sxs-lookup"><span data-stu-id="c287f-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="c287f-117">Utilisez l’outil de ligne de commande Export-CsConfiguration pour sauvegarder les paramètres Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c287f-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="c287f-118">La première étape de la procédure de basculement inclut un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="c287f-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="c287f-119">Il s’agit d’un déplacement forcé car le pool de production n’est pas disponible pour accepter le déplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c287f-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="c287f-120">Le processus de déplacement d’utilisateur Lync Server 2013 est en fait une modification apportée à un attribut sur l’objet de compte d’utilisateur en plus d’une mise à jour de l’enregistrement dans la base de données SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="c287f-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="c287f-121">Ces données peuvent être restaurées à l’aide des deux processus suivants :</span><span class="sxs-lookup"><span data-stu-id="c287f-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="c287f-122">La base de données RTC peut être restaurée à partir du périphérique de vidage de sauvegarde d’origine à partir du serveur SQL de production à l’aide du processus de restauration standard de SQL Server ou à l’aide d’un utilitaire de sauvegarde/restauration tiers.</span><span class="sxs-lookup"><span data-stu-id="c287f-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="c287f-123">Les données de contact utilisateur peuvent être restaurées avec l’utilitaire DBIMPEXP.exe à l’aide du fichier XML qui a été créé à partir de l’exportation SQL Server de production.</span><span class="sxs-lookup"><span data-stu-id="c287f-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="c287f-124">Une fois ces données restaurées, les utilisateurs peuvent se connecter au pool Lync Server 2013 de récupération d’urgence et fonctionner normalement.</span><span class="sxs-lookup"><span data-stu-id="c287f-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="c287f-125">Pour permettre aux utilisateurs de se connecter au pool Lync Server 2013 de récupération d’urgence, une modification d’enregistrement DNS est requise.</span><span class="sxs-lookup"><span data-stu-id="c287f-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="c287f-126">Le pool de production Lync Server 2013 sera référencé par les clients à l’aide de la configuration automatique et des enregistrements SRV DNS suivants :</span><span class="sxs-lookup"><span data-stu-id="c287f-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="c287f-127">SRV : \_ SIP. \_ TLS.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-127">SRV: \_sip.\_tls.\<domain\></span></span> <span data-ttu-id="c287f-128">/CNAME : SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-128">/CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="c287f-129">CNAME : SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-129">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="c287f-130">/cvc-pool-1.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-130">/cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="c287f-131">Pour faciliter le basculement, cet enregistrement CNAMe doit être mis à jour pour référencer le nom de domaine complet du DROCSPool :</span><span class="sxs-lookup"><span data-stu-id="c287f-131">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="c287f-132">CNAME : SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-132">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="c287f-133">/DROCSPool.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-133">/DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="c287f-134">SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-134">Sip.\<domain\></span></span>

  - <span data-ttu-id="c287f-135">Protection.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-135">AV.\<domain\></span></span>

  - <span data-ttu-id="c287f-136">webconf.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-136">webconf.\<domain\></span></span>

  - <span data-ttu-id="c287f-137">OCSServices.\<domain\></span><span class="sxs-lookup"><span data-stu-id="c287f-137">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c287f-138">Pour des procédures d’administration et de gestion détaillées, reportez-vous à la rubrique <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">sauvegarde et restauration de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c287f-138">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c287f-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c287f-139">See Also</span></span>


[<span data-ttu-id="c287f-140">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c287f-140">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="c287f-141">Applets de commande de sauvegarde et de haute disponibilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c287f-141">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="c287f-142">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c287f-142">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="c287f-143">Sauvegarde et restauration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c287f-143">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="c287f-144">Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c287f-144">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


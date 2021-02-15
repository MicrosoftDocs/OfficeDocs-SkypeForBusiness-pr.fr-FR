---
title: Test de récupération d’urgence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Effectuer une récupération système pour un serveur de pool Skype Entreprise Server pour tester votre processus documenté de récupération d’urgence
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832814"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="fe799-103">Test de récupération d’urgence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="fe799-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="fe799-104">Effectuez une récupération système pour un serveur de pool Skype Entreprise Server afin de tester votre processus documenté de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fe799-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="fe799-105">Ce test simule une défaillance matérielle complète pour un serveur et garantit que les ressources, les plans et les données sont disponibles pour la récupération.</span><span class="sxs-lookup"><span data-stu-id="fe799-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="fe799-106">Essayez de faire pivoter le focus du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement.</span><span class="sxs-lookup"><span data-stu-id="fe799-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="fe799-107">Notez que la planification selon laquelle les organisations effectuent des tests de récupération d’urgence varie.</span><span class="sxs-lookup"><span data-stu-id="fe799-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="fe799-108">Il est très important que les tests de récupération d’urgence ne sont pas ignorés ou ignorés.</span><span class="sxs-lookup"><span data-stu-id="fe799-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="fe799-109">Exportez votre topologie, vos stratégies et vos paramètres de configuration Skype Entreprise Server dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="fe799-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="fe799-110">Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème qui a entraîné une perte de données.</span><span class="sxs-lookup"><span data-stu-id="fe799-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="fe799-111">Importez votre topologie, stratégies et paramètres de configuration Skype Entreprise Server dans le magasin central de gestion ou sur l’ordinateur local, comme indiqué dans les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="fe799-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="fe799-112">Pour la protection des données de production :</span><span class="sxs-lookup"><span data-stu-id="fe799-112">To back up production data:</span></span>

- <span data-ttu-id="fe799-113">Sauvegardez les bases de données RTC et LCSLog à l’aide du processus de sauvegarde SQL Server standard pour vider la base de données sur un périphérique de vidage de fichier ou de bande.</span><span class="sxs-lookup"><span data-stu-id="fe799-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="fe799-114">Utilisez une application de sauvegarde tierce pour sauvegarder les données dans un fichier ou sur bande.</span><span class="sxs-lookup"><span data-stu-id="fe799-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="fe799-115">Utilisez la cmdlet Export-CsUserData pour créer une exportation XML de toute la base de données RTC.</span><span class="sxs-lookup"><span data-stu-id="fe799-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="fe799-116">Utilisez la sauvegarde du système de fichiers ou la sauvegarde tierce pour sauvegarder le contenu des réunions et les journaux de conformité.</span><span class="sxs-lookup"><span data-stu-id="fe799-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="fe799-117">Utilisez lExport-CsConfiguration de ligne de commande pour la back up des paramètres Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="fe799-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="fe799-118">La première étape de la procédure de récupération d’urgence comprend un déplacement forcé d’utilisateurs du pool de production vers le pool de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="fe799-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="fe799-119">Il s’agit d’un déplacement forcé, car le pool de production ne sera pas disponible pour accepter le déplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fe799-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="fe799-120">Le processus de déplacement d’utilisateur Skype Entreprise Server est en fait une modification d’un attribut sur l’objet de compte d’utilisateur en plus d’une mise à jour d’enregistrement sur la base de données SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="fe799-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="fe799-121">Ces données peuvent être restaurées à partir du périphérique de vidage de sauvegarde d’origine à partir du SQL Server de production à l’aide du processus de restauration SQL Server standard ou à l’aide d’un utilitaire de sauvegarde/restauration tiers.</span><span class="sxs-lookup"><span data-stu-id="fe799-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="fe799-122">Une fois ces données restaurées, les utilisateurs peuvent effectivement se connecter au pool de récupération d’urgence et fonctionner comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="fe799-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="fe799-123">Pour permettre aux utilisateurs de se connecter au pool de récupération d’urgence, une modification d’enregistrement DNS est requise.</span><span class="sxs-lookup"><span data-stu-id="fe799-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="fe799-124">Le pool Skype Entreprise de production sera référencé par les clients à l’aide de la configuration automatique et des enregistrements DNS SRV des :</span><span class="sxs-lookup"><span data-stu-id="fe799-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="fe799-125">SRV : _sip._tls.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="fe799-126">/CNAME : SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="fe799-127">CNAME : SIP.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="fe799-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="fe799-129">Pour faciliter le perf, cet enregistrement CNAME doit être mis à jour pour référencer le FQDN DROCSPool :</span><span class="sxs-lookup"><span data-stu-id="fe799-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="fe799-130">CNAME : SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="fe799-131">/DROCSPool.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="fe799-132">Sip.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-132">Sip.\<domain></span></span>
- <span data-ttu-id="fe799-133">Av.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-133">AV.\<domain></span></span>
- <span data-ttu-id="fe799-134">webconf.\<domain></span><span class="sxs-lookup"><span data-stu-id="fe799-134">webconf.\<domain></span></span>

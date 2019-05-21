---
title: Test de reprise après sinistre dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Effectuer une récupération du système pour un serveur de pool de serveurs Skype entreprise pour tester votre processus de récupération d’urgence documenté
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279213"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="04f70-103">Test de reprise après sinistre dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="04f70-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="04f70-104">Effectuez une récupération du système pour un serveur de pool de serveurs Skype entreprise pour tester votre processus de récupération d’urgence documenté.</span><span class="sxs-lookup"><span data-stu-id="04f70-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="04f70-105">Ce test simule une panne matérielle complète pour un serveur et permet de garantir la disponibilité des ressources, plans et données pour la récupération.</span><span class="sxs-lookup"><span data-stu-id="04f70-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="04f70-106">Essayez d’alterner l’angle du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement.</span><span class="sxs-lookup"><span data-stu-id="04f70-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="04f70-p102">Notez que le calendrier des tests de récupération d'urgence de votre organisation varie. Il est très important que les tests de récupération d’urgence ne soient ni ignorés ni négligés.</span><span class="sxs-lookup"><span data-stu-id="04f70-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="04f70-109">Exportez votre topologie, vos stratégies et vos paramètres de configuration de Skype entreprise Server vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="04f70-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="04f70-110">Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème ayant entraîné une perte de données.</span><span class="sxs-lookup"><span data-stu-id="04f70-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="04f70-111">Importez vos paramètres de topologie, de stratégies et de configuration de Skype entreprise Server sur le magasin de gestion central ou sur l’ordinateur local, comme illustré dans les commandes suivantes:</span><span class="sxs-lookup"><span data-stu-id="04f70-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="04f70-112">Pour sauvegarder les données de production:</span><span class="sxs-lookup"><span data-stu-id="04f70-112">To back up production data:</span></span>

- <span data-ttu-id="04f70-113">Sauvegardez les bases de données RTC et LCSLog à l’aide du processus de sauvegarde SQL Server standard pour vider la base de données sur un fichier ou un appareil de vidage de bande.</span><span class="sxs-lookup"><span data-stu-id="04f70-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="04f70-114">Sauvegardez les données dans un fichier ou sur une bande à l’aide de l’application de sauvegarde tierce.</span><span class="sxs-lookup"><span data-stu-id="04f70-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="04f70-115">Créez un export XML de la base de données RTC intégrale à l’aide de l’applet de commande Export-CsUserData.</span><span class="sxs-lookup"><span data-stu-id="04f70-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="04f70-116">Utilisez la sauvegarde du système de fichiers ou la sauvegarde tierce pour sauvegarder les journaux du contenu et de la conformité de la réunion.</span><span class="sxs-lookup"><span data-stu-id="04f70-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="04f70-117">Utilisez l’outil de ligne de commande Export-CsConfiguration pour sauvegarder les paramètres de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="04f70-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="04f70-118">La première étape de la procédure de basculement comporte un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="04f70-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="04f70-119">Il s’agit d’un déplacement forcé, car le pool de production n’est pas disponible pour accepter le déplacement des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="04f70-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="04f70-120">Le processus de déplacement d’un utilisateur de Skype entreprise Server est une modification apportée à un attribut sur l’objet compte d’utilisateur, en plus de la mise à jour d’un enregistrement dans la base de données SQL RTC.</span><span class="sxs-lookup"><span data-stu-id="04f70-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="04f70-121">Ces données peuvent être restaurées à partir de l’appareil de vidage de sauvegarde d’origine à partir du serveur SQL Server en utilisant le processus de restauration standard de SQL Server, ou à l’aide d’une utilitaire de sauvegarde/restauration tierce.</span><span class="sxs-lookup"><span data-stu-id="04f70-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="04f70-122">Une fois ces données restaurées, les utilisateurs peuvent se connecter au pool de reprise après sinistre et s’exécuter normalement.</span><span class="sxs-lookup"><span data-stu-id="04f70-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="04f70-123">Pour permettre aux utilisateurs de se connecter au pool de récupération d’urgence, une modification de l’enregistrement DNS sera requise.</span><span class="sxs-lookup"><span data-stu-id="04f70-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="04f70-124">Le pool Skype entreprise de production sera référencé par des clients à l’aide de la configuration automatique et des enregistrements SRV DNS de:</span><span class="sxs-lookup"><span data-stu-id="04f70-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="04f70-125">SRV: _sip. _tls. \<domain>/CNAME: SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="04f70-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="04f70-126">CNAME: SIP. \<domain>/CVC-pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="04f70-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="04f70-127">Pour faciliter le basculement, cet enregistrement CNAME doit être mis à jour de manière à référencer le nom de domaine complet (FQDN) DROCSPool :</span><span class="sxs-lookup"><span data-stu-id="04f70-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="04f70-128">CNAME: SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="04f70-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="04f70-129">/DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="04f70-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="04f70-130">SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="04f70-130">Sip.\<domain></span></span>
- <span data-ttu-id="04f70-131">AV.\<domain></span><span class="sxs-lookup"><span data-stu-id="04f70-131">AV.\<domain></span></span>
- <span data-ttu-id="04f70-132">webconf. \<domain></span><span class="sxs-lookup"><span data-stu-id="04f70-132">webconf.\<domain></span></span>

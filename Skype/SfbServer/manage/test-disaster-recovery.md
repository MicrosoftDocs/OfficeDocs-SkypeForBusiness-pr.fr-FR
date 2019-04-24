---
title: Récupération d’urgence test dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Effectuer une récupération système pour une Skype pour Business server du pool tester votre processus de récupération d’urgence documentée
ms.openlocfilehash: 876470f0e4193f02efe0a2094be80f7bdf891fdd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214735"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="4b95a-103">Récupération d’urgence test dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4b95a-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="4b95a-104">Effectuer une récupération système pour une Skype pour Business server du pool tester votre processus de récupération d’urgence documentée.</span><span class="sxs-lookup"><span data-stu-id="4b95a-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="4b95a-105">Ce test simule une défaillance matérielle complète pour un seul serveur et vous aidera à garantir que les ressources, les plans et les données sont disponibles pour la récupération.</span><span class="sxs-lookup"><span data-stu-id="4b95a-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="4b95a-106">Essayez d’alterner l’angle du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement.</span><span class="sxs-lookup"><span data-stu-id="4b95a-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="4b95a-p102">Notez que le calendrier des tests de récupération d'urgence de votre organisation varie. Il est très important que les tests de récupération d’urgence ne soient ni ignorés ni négligés.</span><span class="sxs-lookup"><span data-stu-id="4b95a-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="4b95a-109">Exporter votre Skype pour la topologie, des stratégies et paramètres de configuration de Business Server vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="4b95a-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="4b95a-110">Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème ayant entraîné une perte de données.</span><span class="sxs-lookup"><span data-stu-id="4b95a-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="4b95a-111">Importer votre Skype pour la topologie du serveur d’entreprise, des stratégies et paramètres de configuration pour le magasin Central de gestion ou sur l’ordinateur local comme indiqué dans les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4b95a-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="4b95a-112">Pour sauvegarder des données de production :</span><span class="sxs-lookup"><span data-stu-id="4b95a-112">To back up production data:</span></span>

- <span data-ttu-id="4b95a-113">Processus pour vider la base de données pour un périphérique de vidage fichier ou la bande de sauvegarde sauvegarder les bases de données RTC et LCSLog à l’aide de SQL Server standard.</span><span class="sxs-lookup"><span data-stu-id="4b95a-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="4b95a-114">Sauvegardez les données dans un fichier ou sur une bande à l’aide de l’application de sauvegarde tierce.</span><span class="sxs-lookup"><span data-stu-id="4b95a-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="4b95a-115">Créez un export XML de la base de données RTC intégrale à l’aide de l’applet de commande Export-CsUserData.</span><span class="sxs-lookup"><span data-stu-id="4b95a-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="4b95a-116">Utilisez la sauvegarde du système de fichiers ou d’une sauvegarde tierce pour sauvegarder les journaux de contenu et de conformité de réunion.</span><span class="sxs-lookup"><span data-stu-id="4b95a-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="4b95a-117">Utilisez l’outil de ligne de commande Export-CsConfiguration pour sauvegarder Skype pour les paramètres du serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4b95a-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="4b95a-118">La première étape de la procédure de basculement comporte un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="4b95a-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="4b95a-119">Il s’agit d’un déplacement forcé, car le pool de production n’est pas disponible pour accepter le déplacement des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4b95a-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="4b95a-120">Le Skype Business Server processus de déplacement utilisateur est en fait une modification apportée à un attribut de l’objet de compte d’utilisateur en plus d’une mise à jour sur la base de données RTC SQL.</span><span class="sxs-lookup"><span data-stu-id="4b95a-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="4b95a-121">Ces données peuvent être restaurées à partir de l’unité de vidage de sauvegarde d’origine de la production SQL Server en utilisant le processus de restauration SQL Server standard ou un tiers sauvegarde/restauration utilitaire.</span><span class="sxs-lookup"><span data-stu-id="4b95a-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="4b95a-122">Après la restauration de ces données, les utilisateurs peuvent effectivement se connectent au pool de la récupération d’urgence et fonctionner comme d’habitude.</span><span class="sxs-lookup"><span data-stu-id="4b95a-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="4b95a-123">Pour permettre aux utilisateurs de se connecter au pool de récupération d’urgence, une modification d’enregistrement DNS seront requise.</span><span class="sxs-lookup"><span data-stu-id="4b95a-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="4b95a-124">Référencée par les clients à l’aide de la configuration automatique et les enregistrements DNS SRV de la production Skype pour le pool d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="4b95a-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="4b95a-125">SRV : _sip._tls. \<domain> /CNAME : SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="4b95a-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="4b95a-126">CNAME : SIP. \<domain> /cvc-pool-1. \<domain></span><span class="sxs-lookup"><span data-stu-id="4b95a-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="4b95a-127">Pour faciliter le basculement, cet enregistrement CNAME doit être mis à jour de manière à référencer le nom de domaine complet (FQDN) DROCSPool :</span><span class="sxs-lookup"><span data-stu-id="4b95a-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="4b95a-128">CNAME : SIP.<domain></span><span class="sxs-lookup"><span data-stu-id="4b95a-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="4b95a-129">/ DROCSPool. \<domain></span><span class="sxs-lookup"><span data-stu-id="4b95a-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="4b95a-130">SIP. \<domain></span><span class="sxs-lookup"><span data-stu-id="4b95a-130">Sip.\<domain></span></span>
- <span data-ttu-id="4b95a-131">Violation d’accès.\<domain></span><span class="sxs-lookup"><span data-stu-id="4b95a-131">AV.\<domain></span></span>
- <span data-ttu-id="4b95a-132">webconf. \<domain></span><span class="sxs-lookup"><span data-stu-id="4b95a-132">webconf.\<domain></span></span>

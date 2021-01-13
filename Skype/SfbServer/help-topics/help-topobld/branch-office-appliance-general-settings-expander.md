---
title: Expanseur des paramètres généraux du Branch Office Appliance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Les sections suivantes vous permettent de modifier les paramètres d’un Survivable Branch Appliance existant ou d’un serveur Survivable Branch Server, les sections suivantes se succèdent :'
ms.openlocfilehash: 95f842e72066f7ef19c474b10f7293f05c83cd67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833204"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="a8d97-103">Expandeur des paramètres généraux du Branch Office Appliance</span><span class="sxs-lookup"><span data-stu-id="a8d97-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="a8d97-104">Les sections suivantes vous permettent de modifier les paramètres d’un Survivable Branch Appliance existant ou d’un serveur Survivable Branch Server, les sections suivantes se succèdent :</span><span class="sxs-lookup"><span data-stu-id="a8d97-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="a8d97-105">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="a8d97-105">General settings</span></span>

- <span data-ttu-id="a8d97-106">Paramètres de résilience</span><span class="sxs-lookup"><span data-stu-id="a8d97-106">Resiliency settings</span></span>

- <span data-ttu-id="a8d97-107">Paramètres du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="a8d97-107">Mediation Server settings</span></span>



<span data-ttu-id="a8d97-108">Dans le cas d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server, vous avez accès aux sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="a8d97-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="a8d97-109">Paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="a8d97-109">General settings</span></span>

<span data-ttu-id="a8d97-p101">Nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement DNS A (hôte) qui corresponde à la nouvelle valeur.</span><span class="sxs-lookup"><span data-stu-id="a8d97-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="a8d97-p102">Vous pouvez choisir **Utiliser toutes les adresses IP configurées** ou **Limiter l’utilisation des services aux adresses IP sélectionnées**. Si vous choisissez **Limiter le service aux adresses IP définies**, vous définissez l’adresse IP principale que le serveur utilisera pour toutes les communications, à l’exception de la passerelle du réseau téléphonique commuté (PSTN). Vous devez définir une adresse IP distincte pour l’utilisation du réseau téléphonique commuté.</span><span class="sxs-lookup"><span data-stu-id="a8d97-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="a8d97-116">Dans **Associations**, vous pouvez modifier ou spécifier les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="a8d97-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="a8d97-117">Associer un serveur d’archivage vous permet de choisir d’associer un serveur d’archivage au Survivable Branch Appliance ou au serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="a8d97-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="a8d97-118">Vous pouvez choisir à partir d’un serveur d’archivage déjà défini en sélectionnant le serveur dans la liste drop-down, ou cliquer sur **Nouveau** pour spécifier un nouveau serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="a8d97-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a8d97-119">Avant de publier la nouvelle topologie que vous venez de définir, le serveur que vous spécifiez doit exister et être joint au domaine.</span><span class="sxs-lookup"><span data-stu-id="a8d97-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="a8d97-120">Associer un serveur de surveillance vous permet de choisir d’associer un serveur de surveillance au Survivable Branch Appliance ou au serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="a8d97-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="a8d97-121">Vous pouvez choisir à partir d’un serveur de surveillance déjà défini en sélectionnant le serveur dans la liste drop-down ou en cliquant sur **Nouveau** pour spécifier un nouveau serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="a8d97-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="a8d97-122">Associer un pool de serveurs Edge vous permet de choisir d’associer un serveur Edge ou un pool de serveurs Edge au Survivable Branch Appliance ou au serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="a8d97-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="a8d97-123">Vous pouvez choisir à partir d’un serveur Edge ou d’un pool de serveurs Edge déjà défini en sélectionnant le serveur dans la liste déroulante, ou vous pouvez cliquer sur **Nouveau** pour indiquer un nouveau serveur Edge ou un pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="a8d97-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="a8d97-124">Résilience</span><span class="sxs-lookup"><span data-stu-id="a8d97-124">Resiliency</span></span>

<span data-ttu-id="a8d97-p106">La résilience apporte une très grande disponibilité au pool de serveurs d’inscriptions. Lorsqu’il est configuré, un serveur d’inscriptions de sauvegarde permet de prendre le relais d’un serveur d’inscriptions en cas d’échec du serveur d’inscriptions principal, permettant aux utilisateurs de se connecter et de communiquer. Il est possible que les utilisateurs ne disposent pas de toutes les fonctionnalités, selon les systèmes qui ont échoué sur le serveur d’inscriptions principal.</span><span class="sxs-lookup"><span data-stu-id="a8d97-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="a8d97-128">Dans la liste de listes listes, sélectionnez le pool frontal Enterprise Edition ou le serveur frontal Standard Edition qui sera le serveur d’inscriptions de sauvegarde pour le Survivable Branch Appliance ou le Serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="a8d97-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="a8d97-129">Vous pouvez également choisir d’activer des intervalles de basculement et de secours.</span><span class="sxs-lookup"><span data-stu-id="a8d97-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="a8d97-130">L’activation des paramètres d’intervalle de basculement et de secours (indiqués en secondes) permet de détecter automatiquement un serveur d’inscriptions défaillant ; un intervalle de secours permet de déterminer automatiquement que le serveur principal est le serveur de sauvegarde et qu’il peut reprendre le processus du serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="a8d97-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8d97-131">Lorsque vous définissez l’intervalle entre deux détections d’échec et de secours, prenez garde à ne pas entrer un intervalle qui provoquera le basculement et le secours si le serveur d’inscriptions ne répond pas pendant un court moment.</span><span class="sxs-lookup"><span data-stu-id="a8d97-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="a8d97-132">Le serveur d’inscriptions peut cesser de répondre pendant de courts moments en fonction du chargement du pool ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="a8d97-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="a8d97-133">Les valeurs par défaut d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans un site pour un pool ou un serveur frontal Standard Edition sont de 120 secondes pour le failover et de 240 secondes pour le serveur de base.</span><span class="sxs-lookup"><span data-stu-id="a8d97-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="a8d97-134">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="a8d97-134">Mediation Server</span></span>

<span data-ttu-id="a8d97-135">Dans le cas du **Serveur de médiation**, vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a8d97-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="a8d97-136">La case à cocher **Activation de la fonctionnalité de cohabitation du serveur de médiation** n’est pas active sur un Survivable Branch Appliance ou un serveur Survivable Branch Server car le serveur de médiation est colocalisé.</span><span class="sxs-lookup"><span data-stu-id="a8d97-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="a8d97-p109">Vous définissez le port d’écoute sur les serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez consulter la configuration requise de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.</span><span class="sxs-lookup"><span data-stu-id="a8d97-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="a8d97-p110">Vous définissez des passerelles PSTN qui sont associées au serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, ces dernières pourront être associées au serveur de médiation. Si vous n’avez défini aucune passerelle, mais si elles sont disponibles pour la définition, vous pouvez sélectionner **Nouveau**. Vous pouvez supprimer des passerelles qui sont déjà configurées pour ce serveur de médiation. Sélectionnez la passerelle, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a8d97-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="a8d97-p111">Si plusieurs passerelles sont associées à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez choisir une autre passerelle comme passerelle par défaut, sélectionnez la passerelle que vous souhaitez utiliser par défaut, puis cliquez sur **Utiliser par défaut**.</span><span class="sxs-lookup"><span data-stu-id="a8d97-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8d97-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8d97-149">See also</span></span>

<span data-ttu-id="a8d97-150">Pour plus d’informations sur la définition et la configuration des paramètres du Survivable Branch Appliance ou du serveur Survivable Branch Server, voir [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="a8d97-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>



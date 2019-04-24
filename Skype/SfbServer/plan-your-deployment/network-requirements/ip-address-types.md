---
title: Configuration des types d’adresse IP dans Skype Entreprise
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Résumé : Passez en revue les considérations de type d’adresse IP ci-dessous avant d’implémenter Skype pour Business Server.'
ms.openlocfilehash: 4ebf8c3329358e526f86dd90eb4cbc0340d06606
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206295"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="9d83c-103">Configuration des types d’adresse IP dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="9d83c-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="9d83c-104">**Résumé :** Passez en revue les considérations de type d’adresse IP ci-dessous avant d’implémenter Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d83c-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="9d83c-105">Vous déployez des types d’adresses IP à l’aide des paramètres de topologie que vous configurez dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9d83c-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="9d83c-106">Cette section décrit comment déployer des types d’adresses IP sur les serveurs frontaux, les serveurs de médiation et serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="9d83c-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="9d83c-107">Déploiement des types d’adresses IP sur un serveur frontal</span><span class="sxs-lookup"><span data-stu-id="9d83c-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="9d83c-108">À l’aide du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9d83c-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="9d83c-109">Pour déployer des types d’adresses IP sur un serveur frontal</span><span class="sxs-lookup"><span data-stu-id="9d83c-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="9d83c-p102">Sous **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**.)</span><span class="sxs-lookup"><span data-stu-id="9d83c-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="9d83c-112">Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer.</span><span class="sxs-lookup"><span data-stu-id="9d83c-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="9d83c-113">Pour une configuration double pile, sélectionnez **Activer le IPv4** et **Activer IPv6**.</span><span class="sxs-lookup"><span data-stu-id="9d83c-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="9d83c-114">**Boîte de dialogue Modifier les propriétés du pool de serveurs frontaux**</span><span class="sxs-lookup"><span data-stu-id="9d83c-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="9d83c-p104">**Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="9d83c-117">Cette option est recommandée pour les configurations IP version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="9d83c-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="9d83c-p105">**Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour **Adresse IP principale**.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="9d83c-p106">**Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="9d83c-p107">**Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="9d83c-127">L’installation des cartes d’interface réseau supplémentaire (NIC) pour prendre en charge la configuration d’adresse IP PSTN (ou pour toute autre raison) sur les serveurs frontaux n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9d83c-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="9d83c-128">Pour plus d’informations sur les configurations de carte réseau pris en charge pour Skype pour Business Server, voir [plateformes matérielles de serveur pour Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="9d83c-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="9d83c-129">Déploiement des types d’adresse IP sur un serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9d83c-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="9d83c-130">À l’aide du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="9d83c-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="9d83c-131">Pour déployer des types d’adresses IP sur un serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9d83c-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="9d83c-132">Dans le Générateur de topologie, sous **pools de médiation**, cliquez sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9d83c-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="9d83c-133">(Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)</span><span class="sxs-lookup"><span data-stu-id="9d83c-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="9d83c-p110">Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="9d83c-136">**Boîte de dialogue Modifier les propriétés du pool de serveurs de médiation**</span><span class="sxs-lookup"><span data-stu-id="9d83c-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="9d83c-p111">**Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d83c-139">Cette option est recommandée pour les configurations IP version 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="9d83c-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="9d83c-p112">**Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour Adresse IP principale.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="9d83c-p113">**Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="9d83c-p114">**Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9d83c-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9d83c-149">Nous seulement prend en charge deux cartes réseau *dédié* serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="9d83c-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="9d83c-150">Si le rôle Sserveur de médiation est colocalisé sur le serveur frontal, puis les cartes réseau doubles ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9d83c-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="9d83c-151">Pour plus d’informations sur les configurations de carte réseau pris en charge pour Skype pour Business Server 2015, voir [configuration matérielle pour Skype pour Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="9d83c-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="9d83c-152">Pour plus d’informations sur les configurations de carte réseau pris en charge pour Skype pour Business Server 2019, voir [configuration matérielle pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="9d83c-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="9d83c-153">Déploiement des types d’adresse IP sur un serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9d83c-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="9d83c-154">À l’aide du Générateur de topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9d83c-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="9d83c-155">Pour déployer des types d’adresses IP sur un serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9d83c-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="9d83c-156">Dans le Générateur de topologie, sous **pools de serveurs Edge**, cliquez sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9d83c-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="9d83c-157">(Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** à partir du menu **Action**.)</span><span class="sxs-lookup"><span data-stu-id="9d83c-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="9d83c-158">Dans la fenêtre **Modifier les propriétés**, sélectionnez la configuration d’adresse IP à prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="9d83c-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="9d83c-159">Pour chaque type d’adresse sélectionné, vous devez fournir des adresses internes et externes appropriées.</span><span class="sxs-lookup"><span data-stu-id="9d83c-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

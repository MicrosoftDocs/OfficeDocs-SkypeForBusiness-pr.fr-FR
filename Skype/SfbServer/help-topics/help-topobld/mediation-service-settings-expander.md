---
title: Expanseur des paramètres du service de médiation
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
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Pour le serveur de médiation, vous pouvez spécifier les données suivantes :'
ms.openlocfilehash: 60312afc4ab487be474eeef6a8432e3522058275
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104420"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="c0306-103">Expandeur des paramètres du service de médiation</span><span class="sxs-lookup"><span data-stu-id="c0306-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="c0306-104">Pour **Serveur de médiation**, vous pouvez spécifier les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="c0306-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="c0306-105">Si vous coloquez le serveur de médiation sur le pool frontal ou le serveur Standard Edition Server, activez la case à cocher Serveur de médiation **cochez la case .**</span><span class="sxs-lookup"><span data-stu-id="c0306-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="c0306-106">Si vous choisissez de ne pas colocaliser le serveur de médiation, cette section ne comporte aucun paramètre définissable.</span><span class="sxs-lookup"><span data-stu-id="c0306-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="c0306-p102">Si vous avez activé la colocalisation du serveur de médiation, vous devez définir la plage de ports d’écoute du serveur pour le protocole TLS (Transport Layer Security). Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP (Transmission Control Protocol) pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.</span><span class="sxs-lookup"><span data-stu-id="c0306-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="c0306-p103">Vous définissez les passerelles PSTN qui sont associées au serveur de médiation colocalisé. Si vous avez déjà défini des passerelles, ces dernières pourront être associées au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c0306-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="c0306-p104">Si plusieurs passerelles sont associées à un serveur de médiation, la première passerelle associée sera la passerelle par défaut. Si vous devez choisir une autre passerelle comme passerelle par défaut, sélectionnez la passerelle que vous souhaitez utiliser par défaut, puis cliquez sur **Utiliser par défaut**. Pour désélectionner la passerelle par défaut, cliquez sur **Annuler Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="c0306-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="c0306-117">Pour plus d’informations sur la définition et la configuration des paramètres du pool frontal Enterprise Edition ou du serveur Standard Edition, voir [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).</span><span class="sxs-lookup"><span data-stu-id="c0306-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).</span></span>
---
title: Expanseur des paramètres généraux du serveur de médiation pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue. Sur le côté gauche, un jeu de liens vous permet d’accéder aux paramètres généraux, aux paramètres du tronçon suivant et aux paramètres de la passerelle PSTN. Les paramètres suivants se trouvent dans chaque section :'
ms.openlocfilehash: db7964826a50f462435769d66ddfab3804462541
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806744"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="1ac57-105">Expandeur des paramètres généraux du serveur de médiation pour Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1ac57-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="1ac57-106">Vous modifiez les propriétés des serveurs de médiation dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1ac57-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="1ac57-107">Sur le côté gauche, un jeu de liens vous permet d’accéder aux paramètres généraux, aux paramètres du tronçon suivant et aux paramètres de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ac57-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="1ac57-108">Les paramètres suivants se trouvent dans chaque section :</span><span class="sxs-lookup"><span data-stu-id="1ac57-108">In each section are the following settings:</span></span>

 <span data-ttu-id="1ac57-109">**Général**:</span><span class="sxs-lookup"><span data-stu-id="1ac57-109">**General**:</span></span>

- <span data-ttu-id="1ac57-110">**Nom de domaine complet :** vous modifiez le nom de domaine complet du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="1ac57-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="1ac57-111">**Associations**: cochez la case Associer un pool de serveurs Edge (pour les **composants multimédias)** et sélectionnez un serveur Edge ou un pool de serveurs Edge pour le serveur de médiation à utiliser comme chemin d’accès multimédia pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="1ac57-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="1ac57-112">**Tronçon suivant** :</span><span class="sxs-lookup"><span data-stu-id="1ac57-112">**Next hop**:</span></span>

- <span data-ttu-id="1ac57-113">**Sélection du saut** suivant : sélectionnez dans une liste le serveur frontal ou le pool frontal à utiliser comme chemin d’accès pour le serveur de médiation à utiliser pour communiquer avec votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1ac57-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="1ac57-114">**Passerelle PSTN** :</span><span class="sxs-lookup"><span data-stu-id="1ac57-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="1ac57-115">**Passerelle PSTN du serveur de médiation** :</span><span class="sxs-lookup"><span data-stu-id="1ac57-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="1ac57-116">**Ports d’écoute**: définissez les ports que le serveur de médiation écoutera.</span><span class="sxs-lookup"><span data-stu-id="1ac57-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="1ac57-117">Vous pouvez définir un port pour le protocole **TLS** (Transport Layer Security) ou **TCP** (Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="1ac57-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="1ac57-118">Pour que l’entrée du port TCP soit disponible, vous devez activer la case à cocher **Activer le port TCP**.</span><span class="sxs-lookup"><span data-stu-id="1ac57-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1ac57-119">Consultez la documentation et les paramètres de configuration de votre passerelle de réseau téléphonique commuté (PSTN) pour déterminer si vous devez activer et définir les valeurs du port TLS, TCP ou les deux.</span><span class="sxs-lookup"><span data-stu-id="1ac57-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="1ac57-120">TLS est un protocole plus sécurisé, qui utilise des certificats pour chiffrer le trafic entre le serveur de médiation et la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ac57-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="1ac57-121">Certaines passerelles PSTN ne prennent pas en charge TLS.</span><span class="sxs-lookup"><span data-stu-id="1ac57-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="1ac57-122">Il existe une liste de jonctions SIP et de passerelles qui sont définies et configurées pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1ac57-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="1ac57-123">Si aucune entrée n’est présente, aucune jonction SIP ou passerelles PSTN n’est configurée pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1ac57-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="1ac57-124">Vous définissez et configurez les passerelles et les trunks sous **Composants partagés** dans le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="1ac57-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ac57-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ac57-125">See also</span></span>

[<span data-ttu-id="1ac57-126">Vue d’ensemble d’une jonction SIP</span><span class="sxs-lookup"><span data-stu-id="1ac57-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="1ac57-127">Options de déploiement d’une passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="1ac57-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)

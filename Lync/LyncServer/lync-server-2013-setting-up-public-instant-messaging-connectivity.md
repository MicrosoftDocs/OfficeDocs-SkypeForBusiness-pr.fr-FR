---
title: 'Lync Server 2013 : Configuration de la connectivité PIC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="3f186-102">Configuration de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f186-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f186-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3f186-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3f186-104">Si votre organisation veut prendre en charge la connectivité de messagerie instantanée publique avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat.</span><span class="sxs-lookup"><span data-stu-id="3f186-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="3f186-105">À la place, suivez les étapes de la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="3f186-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="3f186-106">Configuration de la connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="3f186-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="3f186-107">Sur un serveur frontal, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3f186-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="3f186-108">Développez pools de bords, puis cliquez avec le bouton droit sur votre serveur Edge ou sur le pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="3f186-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="3f186-109">Sélectionnez modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="3f186-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="3f186-110">Dans modifier les propriétés sous général, sélectionnez Activer la Fédération pour ce pool Edge (port 5061).</span><span class="sxs-lookup"><span data-stu-id="3f186-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="3f186-111">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="3f186-111">Click OK.</span></span>

3.  <span data-ttu-id="3f186-112">Cliquez sur action, sélectionnez topologie, puis publier.</span><span class="sxs-lookup"><span data-stu-id="3f186-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="3f186-113">Lorsque le système vous le demande, cliquez sur suivant.</span><span class="sxs-lookup"><span data-stu-id="3f186-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="3f186-114">Lorsque la publication est terminée, cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="3f186-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="3f186-115">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f186-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="3f186-116">Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f186-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="3f186-117">Cliquez de nouveau sur Exécuter.</span><span class="sxs-lookup"><span data-stu-id="3f186-117">Click Run Again.</span></span>

5.  <span data-ttu-id="3f186-118">Dans configurer les composants serveur Lync, cliquez sur suivant.</span><span class="sxs-lookup"><span data-stu-id="3f186-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="3f186-119">L’écran de synthèse indique les actions à mesure qu’elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="3f186-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="3f186-120">Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="3f186-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="3f186-121">Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="3f186-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="3f186-122">Pour créer une demande de certificat pour l’interface externe du serveur de périphérie pour la prise en charge de la connectivité de messagerie instantanée publique avec AOL</span><span class="sxs-lookup"><span data-stu-id="3f186-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="3f186-123">Lorsque le modèle requis est disponible pour l’autorité de certification, utilisez la cmdlet Windows PowerShell suivante à partir du serveur de périphérie pour demander le certificat.</span><span class="sxs-lookup"><span data-stu-id="3f186-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="3f186-124">Le nom du certificat par défaut du modèle utilisé pour Lync Server est le serveur Web.</span><span class="sxs-lookup"><span data-stu-id="3f186-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="3f186-125">Spécifiez le \<nom\> du modèle uniquement si vous devez utiliser un modèle différent du modèle par défaut.</span><span class="sxs-lookup"><span data-stu-id="3f186-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3f186-126">Si votre organisation veut prendre en charge une connectivité de messagerie instantanée publique avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit affecté au bord externe du service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="3f186-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="3f186-127">En effet, le modèle de serveur Web d’autorité de certification utilisé par l’Assistant Certificat pour demander un certificat ne prend pas en charge la configuration améliorée de l’utilisation du client.</span><span class="sxs-lookup"><span data-stu-id="3f186-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="3f186-128">Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de l’utilisation du client.</span><span class="sxs-lookup"><span data-stu-id="3f186-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : configuration de la connectivité PIC (public Instant Messaging Connectivity)'
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
ms.openlocfilehash: ab2c3cfec8a685251a3a1627392d6d4eb9691748
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521831"
---
# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="141f2-102">Configuration de la connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="141f2-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="141f2-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="141f2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="141f2-p101">Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat. À la place, effectuez les étapes de la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="141f2-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="141f2-106">Configuration de la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="141f2-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="141f2-p102">Sur le serveur frontal, ouvrez le Générateur de topologie. Développez les pools Edge, puis cliquez avec le bouton droit sur votre serveur Edge ou votre pool de serveurs Edge. Sélectionnez Modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="141f2-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="141f2-p103">Dans Modifier les propriétés sous Général, sélectionnez Activer la fédération pour ce pool Edge (port 5061). Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="141f2-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="141f2-p104">Cliquez sur Action, sélectionnez Topologie, puis Publier. Dans la page Publier la topologie, cliquez sur Suivant. Quand la publication est terminée, cliquez sur Terminer.</span><span class="sxs-lookup"><span data-stu-id="141f2-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="141f2-p105">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.</span><span class="sxs-lookup"><span data-stu-id="141f2-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="141f2-p106">Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="141f2-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="141f2-122">Pour créer une demande de certificat pour l’interface externe du serveur Edge, afin de prendre en charge la connectivité PIC avec AOL</span><span class="sxs-lookup"><span data-stu-id="141f2-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="141f2-123">Lorsque le modèle requis est à la disposition de l’autorité de certification, utilisez l’applet de commande Windows PowerShell suivante depuis le serveur Edge pour demander le certificat :</span><span class="sxs-lookup"><span data-stu-id="141f2-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="141f2-124">Le nom de certificat par défaut du modèle utilisé pour Lync Server est le serveur Web.</span><span class="sxs-lookup"><span data-stu-id="141f2-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="141f2-125">Spécifiez uniquement le \<template name\> si vous devez utiliser un modèle qui est différent du modèle par défaut.</span><span class="sxs-lookup"><span data-stu-id="141f2-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="141f2-126">Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit attribué au serveur Edge externe pour le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="141f2-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="141f2-127">Ceci est dû au fait que le modèle Serveur web de l’autorité de certification utilisé par l’Assistant Certificat pour demander un certificat ne prend pas en charge la configuration EKU (utilisation avancée de la clé) sur le client.</span><span class="sxs-lookup"><span data-stu-id="141f2-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="141f2-128">Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de la variable client.</span><span class="sxs-lookup"><span data-stu-id="141f2-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


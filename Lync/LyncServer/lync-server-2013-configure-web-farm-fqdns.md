---
title: 'Lync Server 2013 : Configuration des noms de domaine complets d’une batterie de serveurs web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configuration des noms de domaine complets d’une batterie de serveurs web pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-29_

Lors de la définition de la configuration du serveur Standard Edition Server, du pool frontal ou du pool de directeurs dans le générateur de topologie, vous configurez un nom de domaine complet (FQDN) pour les services Web externes. Pendant le processus de connexion d’un client hébergé sur le serveur Standard Edition ou du pool frontal, les noms de domaine complets configurés pour les services Web sont envoyés par le biais de la mise en service intrabande. Si vous avez besoin d’ajouter ou de modifier l’URL des services Web externes, vous utilisez le générateur de topologie pour configurer ou reconfigurer la configuration des services Web à l’aide de la procédure décrite dans cette rubrique.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Pour configurer un nom de domaine complet du pool externe pour les services Web

1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans le générateur de **topologie, dans**l’arborescence de la console sous les **éditions frontale standard**, cliquez avec le bouton droit sur le nom du **pool, puis**cliquez sur **modifier les propriétés**.

3.  Dans la section **services Web** , ajoutez ou modifiez le **nom de domaine complet des services Web externes**.

4.  Passez en revue et ajustez les **ports Listening** pour HTTP et HTTPS. Les valeurs par défaut sont les suivantes :
    
      - **Ports Listening :** HTTP 8080, HTTPS 4443
    
      - **Ports publiés :** HTTP 80, HTTPS 443
    
    Lorsque le port **Listening** correspond au port sur lequel les services Web externes seront configurés pour recevoir des demandes de la part du proxy inverse, et que les **ports publiés** correspondent aux ports publiés en externe par le proxy inverse et sont communiqués aux clients lors de la mise en service intrabande.

5.  Lorsque vous avez terminé vos ajouts et mises à jour, cliquez sur **OK** pour continuer.

6.  Cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier**.
    
    <div>
    

    > [!IMPORTANT]  
    > Après la publication réussie, un lien vous informant que vous devez effectuer des étapes supplémentaires est peut-être affiché. Le lien, si vous cliquez dessus, ouvre une liste de serveurs affectés par les modifications apportées au générateur de topologie, qui vous oblige à réexécuter l’Assistant Déploiement de Lync Server sur chaque serveur pour mettre à jour la configuration pour les composants ajoutés, supprimés ou modifiés.

    
    </div>

7.  Répétez ces étapes pour chaque serveur Standard Edition, pool frontal, directeur ou pool de directeurs au sein de l’organisation.

</div>

</div>

<span> </span>

</div>

</div>

</div>


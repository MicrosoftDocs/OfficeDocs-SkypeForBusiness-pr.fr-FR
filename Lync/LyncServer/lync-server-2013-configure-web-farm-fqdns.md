---
title: 'Lync Server 2013 : configuration des noms de domaine complets des batteries de serveurs Web'
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
ms.openlocfilehash: 50813855e4181add65ff279933a952116768dcec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configurer les noms de domaine complets des batteries de serveurs Web pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-29_

Lorsque vous avez défini la configuration du serveur Standard Edition, un pool frontal, un directeur ou un pool directeur dans le générateur de topologies, vous configurez un nom de domaine complet (FQDN) des services Web externes. Lors du processus de connexion d’un client hébergé sur le serveur Standard Edition ou le pool frontal, les noms de domaine complets des services Web configurés sont envoyés par le biais de la mise en service intrabande. Si vous avez besoin d’ajouter ou de modifier l’URL des services Web externes, vous utilisez le générateur de topologies pour configurer ou reconfigurer la configuration des services Web à l’aide de la procédure décrite dans cette rubrique.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Pour configurer un nom de domaine complet de pool externe pour les services Web

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans le générateur de topologies, dans l’arborescence de la console, sous les extrémités **frontales Standard Edition**, **serveurs frontaux Enterprise Edition**, et **directeurs**, cliquez avec le bouton droit sur le nom du pool à modifier, puis cliquez sur **modifier les propriétés**.

3.  Dans la section **services Web** , ajoutez ou modifiez le **nom de domaine complet des services Web externes**.

4.  Examinez et ajustez les **ports d’écoute** pour HTTP et HTTPS. Les valeurs par défaut sont les suivantes :
    
      - **Ports d’écoute :** HTTP 8080, HTTPS 4443
    
      - **Ports publiés :** HTTP 80, HTTPS 443
    
    Où les **ports d’écoute** sont le port sur lequel les services Web externes seront configurés pour recevoir les demandes du proxy inverse, et les **ports publiés** sont les ports publiés en externe par le proxy inverse et transmis aux clients lors de la mise en service intrabande.

5.  Lorsque vous avez terminé vos ajouts et mises à jour, cliquez sur **OK** pour continuer.

6.  Cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier**.
    
    <div>
    

    > [!IMPORTANT]  
    > Une fois la publication terminée, un lien vous est présenté pour vous informer qu’il faut effectuer des étapes supplémentaires. Le lien, si vous cliquez dessus, ouvre une liste des serveurs concernés par les modifications apportées dans le générateur de topologies qui vous obligent à réexécuter l’Assistant Déploiement de Lync Server sur chaque serveur répertorié afin de mettre à jour la configuration des composants ajoutés, supprimés ou modifiés.

    
    </div>

7.  Répétez ces étapes pour chaque serveur Standard Edition, pool frontal, directeur ou pool directeur de l’organisation.

</div>

</div>

<span> </span>

</div>

</div>

</div>


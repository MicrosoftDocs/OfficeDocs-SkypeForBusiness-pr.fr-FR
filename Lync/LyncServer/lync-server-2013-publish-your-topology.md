---
title: 'Lync Server 2013 : publication de votre topologie'
description: 'Lync Server 2013 : Publiez votre topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571750"
---
# <a name="publish-your-topology-in-lync-server-2013"></a>Publier votre topologie dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Chaque fois que vous utilisez le générateur de topologies pour créer votre topologie, vous devez publier la topologie dans une base de données du magasin central de gestion afin que les données puissent être utilisées pour déployer Lync Server 2013. Procédez comme suit pour publier votre topologie.

<div>

## <a name="to-publish-the-topology"></a>Pour publier la topologie

1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

2.  Dans le générateur de topologies, dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync 2013**, puis cliquez sur **publier la topologie**.

3.  Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.

4.  Dans la page **Le Générateur de topologie a trouvé un magasin central de gestion**, cliquez sur **Suivant**.

5.  Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.

6.  Dès que l’état indique que la base de données a été correctement créée, procédez comme suit :
    
      - Pour afficher le journal, cliquez sur **Afficher le journal**.
    
      - Pour fermer l’Assistant, cliquez sur **Terminer**.
        
        <div>
        

        > [!IMPORTANT]  
        > S’il s’agit d’une nouvelle installation d’un serveur Edge ou d’un pool de serveurs Edge, vous devez exporter la configuration du serveur Edge à partir d’un serveur frontal existant, d’un pool frontal ou d’un serveur Standard Edition. Pour exporter la configuration, reportez-vous à la rubrique <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export Your Lync Server 2013 Topology et copy it to External Media for Edge installation</A>. Vous allez importer le fichier de configuration à partir du média externe ou du partage réseau pendant la phase de configuration et de déploiement des serveurs Edge via l’Assistant Déploiement de Lync Server.<BR>Une fois que les serveurs Edge sont opérationnels et que la base de données de magasin de gestion de la configuration locale est répliquée avec le déploiement interne, les mises à jour suivantes de la configuration Lync Server 2013 seront publiées et répliquées sur les serveurs Edge.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


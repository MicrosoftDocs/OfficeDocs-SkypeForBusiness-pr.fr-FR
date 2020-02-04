---
title: 'Lync Server 2013 : mise à niveau ou mise à jour des serveurs frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af1680da68299881fe94244969d44fce1900532b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Upgrade or update Front End Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-28_

Les serveurs frontaux d’un pool Enterprise Edition sont organisés en *domaines de mise à niveau*. Il s’agit de sous-ensembles de serveurs frontaux dans la liste. Les domaines de mise à niveau sont créés automatiquement par le générateur de topologie.

Lorsque vous procédez à la mise à niveau de vos serveurs, vous devez effectuer la mise à niveau d’un domaine à la fois. Mettez à niveau chaque serveur d’un domaine de mise à niveau, mettez-le à niveau, puis redémarrez-le avant de passer à un autre domaine de mise à niveau. Assurez-vous de garder une trace des domaines et serveurs de mise à niveau que vous avez mis à niveau jusqu’ici. Utilisez le diagramme de flux suivant lors de la mise à niveau de chaque serveur.

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Mise à niveau ou mise à jour des serveurs front-end":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Pour appliquer une mise à niveau aux serveurs frontaux d’un pool

1.  Sur un serveur frontal du pool, exécutez l’applet de commande suivante :
    
    **Get-CsPoolUpgradeReadinessState**
    
    Si la valeur de *PoolUpgradeState* est **occupé**, attendez 10 minutes, puis réessayez de **Get-CsPoolUpgradeReadinessState** . Si vous voyez **occupé** au moins trois temps consécutifs, après 10 minutes entre chaque tentative, ou si vous voyez un résultat de **InsufficientActiveFrontEnds** pour **PoolUpgradeState,** il y a un problème avec le pool. Si ce pool est associé à un autre pool frontal dans une topologie de récupération d’urgence, vous devez faire basculer le pool vers le pool de sauvegarde, puis mettre à jour les serveurs dans ce pool. Pour plus d’informations, reportez-vous à [échec d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Si la valeur de *PoolUpgradeState* est **prête**, passez à l’étape 2.

2.  L’applet **de passe Get-CsPoolUpgradeReadinessState** renvoie également des informations sur chaque domaine de mise à niveau du pool et sur les serveurs frontaux de chaque domaine de mise à niveau. Si la valeur **ReadyforUpgrade** est **true** pour le domaine de mise à niveau qui contient le ou les serveurs que vous voulez mettre à niveau, vous pouvez les mettre à niveau en toute sécurité. Pour cela, procédez comme suit :
    
    1.  Arrêtez les nouvelles connexions aux serveurs frontaux que vous allez mettre à niveau en utilisant `Stop-CsWindowsService -Graceful -Verbose` l’applet de commande.
        
        <div>
        

        > [!NOTE]  
        > Si vous exécutez ces mises à niveau de serveur pendant une période d’inactivité du serveur planifié, vous pouvez exécuter cette applet de commande sans le paramètre'-<STRONG>douceur</STRONG>'comme suit : <STRONG>Stop-CsWindowsService</STRONG>. Cela arrêtera immédiatement les services, sans attendre le remplissage de toutes les demandes de service existantes.

        
        </div>
    
    2.  Mettez à niveau les serveurs associés à ce domaine de mise à niveau.
    
    3.  Redémarrez les serveurs et assurez-vous qu’ils acceptent de nouvelles connexions.

3.  Répétez les étapes 1 et 2 pour chaque autre domaine de mise à niveau de la liste, jusqu’à ce que tous les serveurs front-end aient été mis à niveau.

</div>

</div>

<span> </span>

</div>

</div>

</div>


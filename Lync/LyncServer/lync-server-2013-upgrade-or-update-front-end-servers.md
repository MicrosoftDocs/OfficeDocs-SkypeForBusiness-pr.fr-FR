---
title: 'Lync Server 2013 : mise à niveau ou mise à jour des serveurs frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530321"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Mettre à niveau ou mettre à jour des serveurs frontaux dans Lync Server 2013

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-28_

Les serveurs frontaux d’un pool Enterprise Edition sont organisés en *domaines de mise à niveau*. Il s’agit de sous-ensembles des serveurs frontaux dans le pool. Les domaines de mise à niveau sont créés automatiquement par le générateur de topologie.

Lors de la mise à niveau des serveurs, vous devez effectuer un domaine de mise à niveau à la fois. Mettez chaque serveur dans un domaine de mise à niveau vers le bas, mettez-le à niveau, puis redémarrez-le avant de passer à un autre domaine de mise à niveau. N’oubliez pas de suivre les domaines et les serveurs de mise à niveau que vous avez mis à niveau jusqu’à présent. Utilisez l’organigramme suivant lors de la mise à niveau de chaque serveur.

![Mise à niveau ou mise à jour des serveurs frontaux](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Pour appliquer une mise à niveau sur les serveurs frontaux dans un pool

1.  Sur le serveur frontal du pool, exécutez l’applet de commande suivant :
    
    **Get-CsPoolUpgradeReadinessState**
    
    Si la valeur de *PoolUpgradeState* est **Busy**, patientez 10 minutes, puis réessayez d' **accéder à CsPoolUpgradeReadinessState** . Si vous voyez **occupé** pendant au moins trois heures consécutives, après avoir attendu 10 minutes entre chaque tentative, ou si vous constatez un résultat de **InsufficientActiveFrontEnds** pour **PoolUpgradeState,** cela signifie qu’il y a un problème avec le pool. Si ce pool est couplé avec un autre pool frontal dans une topologie de récupération d’urgence, basculez ce pool vers le pool de sauvegarde, puis mettez à jour les serveurs de ce pool. Pour plus d’informations, reportez-vous à [basculement d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Si la valeur de *PoolUpgradeState* est **Ready**, passez à l’étape 2.

2.  L’applet de commande **Get-CsPoolUpgradeReadinessState** renvoie également des informations sur chaque domaine de mise à niveau dans le pool et sur les serveurs frontaux se situant dans chaque domaine de mise à niveau. Si la valeur **ReadyforUpgrade** est **true** pour le domaine de mise à niveau qui contient le ou les serveurs que vous souhaitez mettre à niveau, vous pouvez mettre à niveau ces serveurs en toute sécurité maintenant. Pour ce faire, procédez de la façon suivante :
    
    1.  Arrêtez les nouvelles connexions sur les serveurs frontaux que vous allez mettre à niveau à l’aide de l’applet de commande `Stop-CsWindowsService -Graceful -Verbose` .
        
        <div>
        

        > [!NOTE]  
        > Si vous effectuez ces mises à niveau de serveur pendant une période d’indisponibilité du serveur planifiée, vous pouvez exécuter cette applet de commande sans le paramètre « -<STRONG>gracieuse</STRONG>», comme suit : <STRONG>Stop-CsWindowsService</STRONG>. Cela arrêtera immédiatement les services, sans attendre le remplissage de toutes les demandes de service existantes.

        
        </div>
    
    2.  Mettez à niveau les serveurs associés à ce domaine de mise à niveau.
    
    3.  Redémarrez les serveurs et assurez-vous qu’ils acceptent de nouvelles connexions.

3.  Répétez les étapes 1 et 2 pour chaque autre domaine de mise à niveau dans le pool, jusqu’à ce que tous les serveurs frontaux aient été mis à niveau.

</div>

</div>

<span> </span>

</div>

</div>

</div>


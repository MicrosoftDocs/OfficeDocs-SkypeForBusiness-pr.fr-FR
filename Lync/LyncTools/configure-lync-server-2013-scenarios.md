---
title: Configurer des scénarios Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789c3ee8c18b5fb0e92ef9a520152644bebbdde1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>Configurer des scénarios Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-28_

Pour exécuter l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), la topologie Lync Server 2013 doit d’abord être configurée pour les scénarios qui seront exécutés. Si Lync Server 2013 n’est pas configuré ou a été configuré de manière incorrecte, la simulation de charge ne fonctionnera pas dans la plupart des cas. Grâce à l’outil de stress et de performances de Lync Server 2013, nous avons fourni des exemples de fichiers de ressources de base et de scripts Lync Server Management Shell qui peuvent servir de point de départ pour la configuration de Lync Server 2013. Cette rubrique décrit les exemples Windows PowerShell proposés. Notez qu’il ne s’agit pas de la rubrique permettant de décrire la configuration de Lync Server 2013 en général. Pour plus d’informations sur l’utilisation de Windows PowerShell dans Lync Server 2013, consultez la documentation Lync Server <https://technet.microsoft.com/en-us/library/gg398474.aspx>Management Shell à l’adresse.

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>À propos de l’exécution de scripts Lync Server Management Shell

Nous avons fourni des exemples de scripts Lync Server Management Shell qui peuvent être utilisés en préparation pour exécuter la simulation de charge. Étant donné que les scripts sont destinés à une simulation de charge, ils sont simples et permissif, et par conséquent, peuvent ne pas être appropriés pour la production. Tous les scripts sont des exemples qui doivent être examinés et, dans certains cas, modifiés pour refléter votre topologie. Au minimum, nous pensons que le scénario de service de Response Group (RGS) doit être modifié pour spécifier les agents affectés aux groupes d’agents. Toutefois, vous avez la possibilité de ne pas simuler ce chargement.

<div>


> [!WARNING]  
> Prenez soin de revoir et de comprendre les exemples fournis. Les scripts écrasent les paramètres existants dans la topologie.



</div>

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell et de Lync Server Management Shell, voir le blog Lync Server <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>2013 Windows PowerShell à l’adresse.



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Monikers de la version du client d’outils de stress et de performance

Il est possible que vous deviez configurer la stratégie de vérification de la version du client si vous avez modifié les paramètres des valeurs par défaut. Pour plus d’informations, consultez la section « Configuration des versions <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>clientes prises en charge » à l’adresse. L’outil contraintes et performances de Lync Server 2013 utilise les versions d’agent utilisateur suivantes par défaut lors de la communication avec Lync Server 2013 :

  - LSPT/15.0.0.0 (outil de stress et de performance de Lync Server 2013)

  - OCPHONE/.0.522

Celles-ci sont destinées au client Mobility (UCWA) dans LyncPerfTool :

  - Outil de performance/conférence Web Ucwa

  - Outil perf Ucwa/mobile

</div>

</div>

<span> </span>

</div>

</div>

</div>


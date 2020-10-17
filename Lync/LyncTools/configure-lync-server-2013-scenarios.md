---
title: Configurer les scénarios Lync Server 2013
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
ms.openlocfilehash: d108cc3a2c49c40eb04c9039c83689fb8c5abf4c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499941"
---
# <a name="configure-lync-server-2013-scenarios"></a>Configurer les scénarios Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-28_

Pour exécuter l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool), la topologie Lync Server 2013 doit d’abord être configurée pour les scénarios qui seront exécutés. Si Lync Server 2013 n’est pas configuré ou qu’il est configuré de manière incorrecte, la simulation de charge échoue dans la plupart des cas. Avec l’outil de contrainte et de performances de Lync Server 2013, nous avons fourni un exemple de scripts Lync Server Management Shell et de fichiers de ressources de base qui peuvent être utilisés comme point de départ pour la configuration de Lync Server 2013. Cette rubrique décrit les exemples Windows PowerShell fournis. Notez qu’il ne s’agit pas de l’objectif de cette rubrique, qui explique comment configurer Lync Server 2013 en général. Pour plus d’informations sur l’utilisation de Windows PowerShell dans Lync Server 2013, reportez-vous à la documentation Lync Server Management Shell à l’adresse <https://technet.microsoft.com/library/gg398474.aspx> .

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>À propos de l’exécution de scripts Lync Server Management Shell

Nous avons fourni des exemples de scripts Lync Server Management Shell pouvant être utilisés en préparation à l’exécution de la simulation de charge. Étant donné que les scripts sont destinés à la simulation de charge, ils sont simples et permissants et, par conséquent, peuvent ne pas être appropriés pour la production. Tous les scripts sont des exemples et doivent être examinés, et, dans certains cas, modifiés pour refléter votre topologie. Au minimum, nous prévoyons que le scénario de service Response Group (RGS) doit être modifié pour spécifier les agents affectés aux groupes d’agents. Toutefois, vous avez la possibilité de ne pas simuler cette charge.

<div>


> [!WARNING]  
> Veillez à examiner et à comprendre les exemples fournis. Les scripts remplacent tous les paramètres existants dans la topologie.



</div>

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell et de Lync Server Management Shell, voir le blog Lync Server 2013 Windows PowerShell à l’adresse <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>Monikers de version du client outil de stress et de performance

Vous devrez peut-être configurer la stratégie de vérification de la version du client si vous avez modifié les valeurs par défaut. Pour plus d’informations, voir « Configuration des versions de clients prises en charge » à l’adresse <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> . L’outil de contrainte et de performances de Lync Server 2013 utilise par défaut les versions suivantes de l’agent utilisateur lors de la communication avec Lync Server 2013 :

  - LSPT/15.0.0.0 (outil de contrainte et de performances de Lync Server 2013)

  - OCPHONE/.0.522

Celles-ci sont destinées au client Mobility (UCWA) dans LyncPerfTool :

  - Outil perf Ucwa/conférence Web

  - Outil de performances Ucwa/mobile

</div>

</div>

<span> </span>

</div>

</div>

</div>


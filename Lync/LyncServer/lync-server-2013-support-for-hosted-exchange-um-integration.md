---
title: Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24139ad5294bf908a85b797300397fa8b2ac9140
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

L’application de routage ExUM Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange dans un environnement local dans lequel Lync Server 2013 et la messagerie unifiée Exchange sont tous deux installés localement au sein de votre entreprise, ou dans avec la messagerie unifiée Exchange hébergée par un fournisseur de services, comme indiqué dans le schéma suivant.

![Déploiement de la messagerie unifiée Exchange Server en local](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement de la messagerie unifiée Exchange Server en local")

Les modes suivants sont pris en charge :

  - **Le mode**   local Lync Server 2013 et Exchange um sont tous deux déployés sur des serveurs locaux au sein de votre entreprise.

  - **Mode local Lync**   Server 2013 est déployé sur des serveurs locaux au sein de votre entreprise et la messagerie unifiée Exchange est hébergée dans la fonction d’un fournisseur de services en ligne, par exemple un centre de données Microsoft Exchange Online.

  - **Mode mixte votre**   déploiement de Lync Server 2013 comporte certaines boîtes aux lettres utilisateur hébergées sur des serveurs locaux exécutant Microsoft Exchange Server au sein de votre entreprise et certaines boîtes aux lettres dans un centre de données de service Exchange hébergé.
    
    <div>
    

    > [!NOTE]  
    > Le mode mixte peut être utilisé en tant que solution de transition lors de l’évaluation et de la migration par le biais des utilisateurs vers la messagerie unifiée Exchange hébergée, ou sous la forme d’une solution permanente si vous choisissez de limiter les services de messagerie unifiée d’utilisateurs Exchange après la migration d’autres utilisateurs.

    
    </div>

Pour intégrer Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez configurer un *espace d’adressage SIP partagé* (également appelé *domaine fractionné*). Dans cette configuration, Lync Server 2013 et le fournisseur de service de messagerie unifié Exchange hébergés par des tiers peuvent accéder au même espace d’adressage de domaine SIP. Pour plus d’informations, reportez-vous à la section [architecture d’intégration de MU Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) dans la documentation de planification.

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013 : problèmes avec le test de l’environnement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39dfbdfbe430c7c334eaab37bf0ab0e048a84ba4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Problèmes avec le test de l’environnement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Best Practices Analyzer vous permet de vérifier que votre environnement Lync Server 2013 est une configuration prise en charge. Dans le cadre des vérifications des services de domaine Active Directory, Best Practices Analyzer permet :

  - de vérifier la préparation de la forêt et du schéma des services de domaine Active Directory ;

  - d’identifier le nombre de domaines et de sites de services de domaine Active Directory du déploiement ;

  - de vérifier les niveaux du domaine et de la forêt ;

  - de vérifier la version du contrôleur de domaine ;

  - d’identifier le contexte d’appellation du domaine, de la configuration et du schéma ;

  - d’identifier le nombre d’utilisateurs autorisés ;

  - de vérifier où les paramètres des services de domaine Active Directory sont stockés ;

  - Recherche les points de connexion de service (SCP) pour Lync Server.

  - d’identifier la version de la base de données.

<div>

## <a name="resolving-issues-with-the-environment"></a>Résolution des problèmes avec l’environnement

Si l’environnement de test détecte des problèmes avec votre environnement, ces problèmes sont probablement causés par d’autres problèmes avec votre configuration d’Active Directory ou le niveau du logiciel exécuté sur des serveurs spécifiques. Par exemple, si Best Practices Analyzer identifie un contrôleur de domaine de votre environnement exécutant Windows Server 2000, il émettra un avertissement et vous devrez mettre à niveau ces contrôleurs de domaine vers une version prise en charge de Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>


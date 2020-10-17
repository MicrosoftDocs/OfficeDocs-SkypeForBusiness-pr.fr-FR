---
title: 'Lync Server 2013 : vérification de la connectivité pour les utilisateurs externes'
description: 'Lync Server 2013 : Vérifiez la connectivité pour les utilisateurs externes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ef728157d01b93e7d0b8420442ce083a42b5b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547090"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Vérifier la connectivité pour les utilisateurs externes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

La validation de la connectivité pour les utilisateurs externes nécessite de s’assurer de la connectivité des utilisateurs vers le serveur et le port pour le service Edge d’accès.

Le site analyseur de connectivité à distance () est une ressource précieuse pour la confirmation de votre configuration et la possibilité de vous connecter, d’envoyer et de recevoir les messages corrects pour les scénarios requis par l’accès des utilisateurs externes <http://www.testocsconnectivity.com> . Le site est géré et géré par le support Microsoft. Pour accéder à l’Analyseur de connectivité à distance, ouvrez le site web dans un navigateur et suivez les instructions relatives à la sélection du scénario.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Tester la connectivité des utilisateurs externes et de l’accès externe

Les tests d’accès des utilisateurs externes doivent inclure tous les types d’utilisateurs externes pris en charge par votre organisation, dont un ou plusieurs des éléments suivants :

  - Utilisateurs d’au moins un domaine fédéré, et test de la messagerie instantanée, de la présence et du partage du Bureau.

  - Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel le provisionnement a été effectué).

  - Utilisateurs anonymes.

  - Utilisateurs appartenant à votre organisation, qui sont connectés à Lync à distance, mais qui n’utilisent pas VPN.

Ces tests déterminent si votre serveur Edge :

  - Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.
    
      - Exemple : telnet sip.contoso.com 443
    
      - Effectuez le test précédent sur les ports que vous utilisez sur le serveur Edge ou le pool de serveur Edge en fonction de votre déploiement.

  - Effectuer une résolution DNS externe précise.
    
      - Depuis l’extérieur de votre réseau, exécutez la commande ping sur chacun des noms de domaine complets (FQDN) externes de votre serveur Edge ou pool de serveurs Edge. Même si la commande ping échoue, vous obtiendrez les adresses IP que vous pouvez comparer à celles que vous avez affectées.

</div>

</div>

<span> </span>

</div>

</div>

</div>


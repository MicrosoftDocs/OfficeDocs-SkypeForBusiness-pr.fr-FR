---
title: 'Lync Server 2013 : planification des lignes téléphoniques privées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a5381d0f71dd6e15a3b4b6d76f2a03be558b9d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526521"
---
# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Planification des lignes téléphoniques privées avec Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-11_

Lync Server 2013 offre la possibilité de fournir aux utilisateurs une deuxième ligne téléphonique privée en plus de leur ligne téléphonique principale. Les lignes téléphoniques privées sont souvent affectées aux cadres et aux autres qui souhaitent un numéro de téléphone non répertorié auquel ils peuvent être joints directement.

Les lignes téléphoniques privées ne peuvent être configurées qu’avec Lync Server Management Shell. Vous ne pouvez pas configurer de lignes téléphoniques privées avec le panneau de configuration Lync Server. Les lignes téléphoniques privées doivent être configurées uniquement dans les déploiements de Lync Server et non dans des déploiements mixtes.

<div>

## <a name="characteristics-of-private-telephone-lines"></a>Caractéristiques des lignes téléphoniques privées

Bien que le concept de deuxième ligne téléphonique privée soit fondamentalement simple, il est important de comprendre les caractéristiques des lignes privées et les façons dont elles sont similaires et différentes des lignes téléphoniques principales des utilisateurs.

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>Caractéristiques générales des lignes téléphoniques privées

  - Un utilisateur ne peut avoir qu’une seule ligne téléphonique privée.

  - Un utilisateur avec une ligne téléphonique privée n’a qu’une seule boîte aux lettres vocale et reçoit des notifications d’appel en absence à une adresse de messagerie unique.

  - Un utilisateur disposant d’une ligne téléphonique privée ne dispose pas d’une deuxième adresse SIP, et une deuxième ligne téléphonique privée ne donne pas à un utilisateur une fonction de deuxième présence sur le réseau (par exemple, une deuxième identité de messagerie instantanée).

  - Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux. Elles ne sont pas disponibles pour les déploiements hébergés de Lync Server.

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Différences entre les lignes téléphoniques privées et les lignes téléphoniques principales

  - Les numéros de téléphone des lignes téléphoniques privées n’apparaissent pas dans les listes des annuaires téléphoniques ou des contacts qui sont dérivés des services de domaine Active Directory.

  - Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, sonnerie d’équipe, prise d’appel de groupe et application Response Group.

  - Les appels vers une ligne téléphonique privée ont un anneau spécial, et la notification système pour l’appel indique à l’utilisateur que l’appel entrant se trouve sur sa ligne privée.

  - Les appels vers la ligne téléphonique privée sont toujours circulaires. Elles ne suivent pas les règles « ne pas déranger ».

  - Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour effectuer des appels sortants. Lorsqu’un utilisateur avec une ligne téléphonique privée effectue un appel, l’appel provient de la ligne téléphonique principale de l’utilisateur et ne masque pas le nom de l’utilisateur ou le numéro de téléphone principal de l’utilisateur de la personne appelée.

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre les lignes téléphoniques privées et les lignes téléphoniques principales

  - Les appels sans réponse à une ligne téléphonique privée sont routés vers la même boîte de réception de messagerie vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).

  - Le parcage d’appel et la prise d’appel fonctionnent avec des lignes téléphoniques privées exactement de la même manière qu’avec la ligne téléphonique principale de l’utilisateur.

  - Lorsque la sonnerie simultanée est activée sur la ligne téléphonique principale d’un utilisateur, elle est également activée sur la ligne téléphonique privée.

  - Le numéro de téléphone d’une ligne téléphonique privée est enregistré dans l’enregistrement des détails des appels de la même manière que le numéro de téléphone de la ligne téléphonique principale d’un utilisateur, mais avec une indication qu’il s’agit d’un numéro de téléphone privé.

  - Une fois qu’un utilisateur répond à un appel sur une ligne téléphonique privée, l’appel est traité de la même manière qu’un appel sur la ligne téléphonique principale de l’utilisateur. Par exemple, si un utilisateur qui reçoit un appel sur une ligne téléphonique privée transfère l’appel ou invite d’autres personnes à participer à une téléconférence, le nom de l’utilisateur s’affiche dans Lync 2013 et le numéro de téléphone de la ligne téléphonique principale de l’utilisateur apparaît dans ID de l’appelant.

  - Un utilisateur peut dévier un appel (rediriger l’appel vers une autre destination, telle qu’un téléphone mobile ou un téléphone personnel, avant de répondre) à partir de la ligne téléphonique privée de la même manière qu’avec une ligne téléphonique principale.
    
    <div>
    

    > [!NOTE]  
    > Lorsqu’un appel à une ligne privée est acheminé vers un autre numéro de téléphone, le numéro de téléphone de la ligne téléphonique privée est mis à la disposition de l’autre numéro de téléphone et peut être affiché dans les journaux pour ce numéro.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Les appels d’une conférence vers la ligne téléphonique privée n’auront aucune indication de <EM>ligne privée</EM> dans la notification système entrante.

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>Administration des lignes téléphoniques privées

En plus des aspects techniques de la création et de la gestion des lignes téléphoniques privées, vous devrez établir des procédures administratives pour celles-ci. Cela inclut la détermination des stratégies pour les personnes de l’organisation qui sont éligibles pour une ligne privée, la création et la gestion de listes de personnes et de leurs lignes téléphoniques, éventuellement la création d’un annuaire téléphonique privé pour les cadres, la formation des utilisateurs et les tâches associées.

<div>


> [!NOTE]  
> La ligne téléphonique privée est stockée dans Active Directory sous la forme d’un attribut msRTCSIP-PrivateLine sur l’objet de l’utilisateur. Par défaut, tout membre du groupe utilisateurs authentifiés dispose d’un accès en lecture à cet attribut.



</div>

<div>

## <a name="assigning-telephone-numbers"></a>Affectation de numéros de téléphone

Les comptes pour les nouveaux utilisateurs qui ont besoin de lignes téléphoniques privées sont créés de la même manière que les comptes sans ligne téléphonique privée, à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.

Utilisez la cmdlet **Set-Csuser** dans l’environnement de ligne de commande Lync Server Management Shell pour attribuer un numéro de téléphone à une ligne téléphonique privée pour un utilisateur, par exemple, **Set-Csuser-identity "SIP :joe@contoso.com"-PrivateLine "Tél : + 14255551212"**.

Les numéros de téléphone des lignes téléphoniques privées peuvent avoir une longueur comprise entre 3 et 15 chiffres et doivent être précédés du préfixe « TEL : ». Ils peuvent disposer de n’importe quel indicatif régional et de n’importe quel code de pays/région tant que votre organisation dispose d’un accès direct aux codes de zone et de pays/région.

Pour plus d’informations sur les applets de commande et sur Lync Server Management Shell, voir la documentation de [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>Lignes téléphoniques privées dans des déploiements mixtes

Les lignes téléphoniques privées doivent être configurées uniquement pour les déploiements de Lync Server. Dans un déploiement où se trouvent des serveurs Lync Server et Office Communications Server 2007 ou Office Communications Server 2007 R2, lorsqu’un utilisateur d’une version antérieure tente d’appeler une ligne téléphonique privée, le routage de l’appel échoue car le serveur ne peut pas effectuer une recherche inversée de numéros sur une ligne téléphonique privée.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


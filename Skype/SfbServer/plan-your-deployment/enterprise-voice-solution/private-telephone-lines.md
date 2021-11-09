---
title: Planifier des lignes téléphoniques privées avec Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planification des lignes téléphoniques privées (secondaires) dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: a9054266cc5092f77e0fecd66b71b7180c89018c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861081"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planifier des lignes téléphoniques privées avec Skype Entreprise
 
Planification des lignes téléphoniques privées (secondaires) dans Skype Entreprise Server Voix Entreprise.
  
Skype Entreprise Server vous permet d’accorder aux utilisateurs une deuxième ligne téléphonique privée en plus de leur ligne téléphonique principale. Les lignes téléphoniques privées sont souvent attribuées à des cadres et à d’autres personnes qui souhaitent obtenir un numéro de téléphone non listé auquel ils peuvent être joints directement.
  
Les lignes téléphoniques privées ne peuvent être configurées qu’avec Skype Entreprise Server Management Shell. Vous ne pouvez pas configurer de lignes téléphoniques privées avec Skype Entreprise Server panneau de configuration. Les lignes téléphoniques privées doivent être configurées uniquement dans les déploiements de Skype Entreprise Server et non dans les déploiements mixtes.
  
## <a name="characteristics-of-private-telephone-lines"></a>Caractéristiques des lignes téléphoniques privées

Bien que le concept d’une deuxième ligne téléphonique privée soit fondamentalement simple, il est important de comprendre les caractéristiques des lignes privées et les manières dont elles sont similaires et différentes des lignes téléphoniques principales des utilisateurs.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Caractéristiques générales des lignes téléphoniques privées

- Un utilisateur ne peut avoir qu’une seule ligne téléphonique privée.
    
- Un utilisateur avec une ligne téléphonique privée n’a qu’une seule boîte aux lettres vocale et reçoit des notifications d’appel en manque à une seule adresse de messagerie.
    
- Un utilisateur avec une ligne téléphonique privée n’a pas de deuxième adresse SIP et une deuxième ligne téléphonique privée ne donne pas à un utilisateur une deuxième présence sur le réseau (par exemple, une deuxième identité de messagerie instantanée). 
    
- Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux. Ils ne sont pas disponibles avec les déploiements hébergés de Skype Entreprise Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Différences entre les lignes téléphoniques privées et les lignes téléphoniques principales

- Les numéros de téléphone des lignes téléphoniques privées n’apparaissent pas dans les répertoires téléphoniques ou les listes de contacts dérivées des services de domaine Active Directory.
    
- Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, anneau d’équipe, prise d’appel de groupe et application Response Group.
    
- Les appels vers une ligne téléphonique privée ont une sonnerie spéciale et la notification système de l’appel indique à l’utilisateur que l’appel entrant se trouve sur sa ligne privée.
    
- Les appels vers la ligne téléphonique privée sonnent toujours. Ils ne suivent pas les règles « ne pas déranger ».
    
- Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour effectuer des appels sortants. Lorsqu’un utilisateur avec une ligne téléphonique privée passe un appel, l’appel provient de la ligne téléphonique principale de l’utilisateur et ne masque pas le nom de l’utilisateur ou son numéro de téléphone principal à la personne appelée.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitude des lignes téléphoniques privées avec les lignes téléphoniques principales

- Les appels sans réponse vers une ligne téléphonique privée sont acheminés vers la même boîte de réception de messagerie vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).
    
- Le parcage d’appel et la prise d’appel fonctionnent avec des lignes téléphoniques privées exactement de la même manière qu’avec la ligne téléphonique principale de l’utilisateur.
    
- Lorsque la sonnerie simultanée est activée sur la ligne téléphonique principale d’un utilisateur, elle est également activée sur la ligne téléphonique privée.
    
- Le numéro de téléphone d’une ligne téléphonique privée est enregistré dans l’enregistrement des détails des appels de la même manière que le numéro de téléphone de la ligne téléphonique principale d’un utilisateur, mais avec une indication qu’il s’agit d’un numéro de téléphone privé.
    
- Une fois qu’un utilisateur répond à un appel sur une ligne téléphonique privée, l’appel est traité comme un appel sur la ligne téléphonique principale de l’utilisateur. Par exemple, si un utilisateur qui reçoit un appel sur une ligne téléphonique privée le fait suivre ou invite d’autres personnes à une téléconférence, son nom apparaît dans Skype Entreprise et le numéro de téléphone de la ligne téléphonique principale de l’utilisateur apparaît dans l’ID de l’appelant.
    
- Un utilisateur peut appeler (rediriger l’appel vers une autre destination, par exemple, un téléphone mobile ou domicile, avant de répondre) à partir de la ligne téléphonique privée de la même manière qu’avec une ligne téléphonique principale. 
    
    > [!NOTE]
    > Lorsqu’un appel vers une ligne privée est acheminé vers un autre numéro de téléphone, le numéro de téléphone de la ligne privée est mis à la disposition de l’autre numéro de téléphone et peut être affiché dans les journaux de ce numéro. 
  
    > [!NOTE]
    > Les appels d’une conférence vers la  ligne téléphonique privée n’auront pas d’indication de ligne privée dans la notification système entrante.
  
## <a name="administering-private-telephone-lines"></a>Administration des lignes téléphoniques privées

Outre les aspects techniques de la création et de la gestion des lignes téléphoniques privées, vous devez établir des procédures administratives pour ces lignes. Cela inclut la détermination des stratégies pour les personnes de l’organisation éligibles pour une ligne privée, la création et la maintenance de listes de personnes et de leurs lignes téléphoniques, éventuellement la création d’un annuaire téléphonique privé pour les cadres, l’organisation de la formation des utilisateurs et les tâches connexes.
  
> [!NOTE]
> La ligne téléphonique privée est stockée dans Active Directory en tant qu’attribut msRTCSIP-PrivateLine sur l’objet utilisateur. Par défaut, tout membre du groupe Utilisateurs authentifiés dispose d’un accès en lecture à cet attribut. 
  
### <a name="assigning-telephone-numbers"></a>Affectation de numéros de téléphone

 Les comptes des nouveaux utilisateurs qui ont besoin de lignes téléphoniques privées sont créés de la même manière que les comptes sans lignes téléphoniques privées, à l’aide du Panneau de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
Utilisez l’cmdlet **Set-CsUser** dans l’Skype Entreprise Server Management Shell pour affecter un numéro de téléphone à une ligne téléphonique privée pour un utilisateur, par **exemple, Set-CsUser -Identity « sip:joe@contoso.com » -PrivateLine « Tel:+14255551212 »**.
  
Les numéros de téléphone des lignes téléphoniques privées peuvent avoir entre 3 et 15 numéros et doivent être précédés du préfixe « TEL: ». Ils peuvent avoir n’importe quel code régional et n’importe quel code de pays/région tant que votre organisation dispose d’une numérotation directe à l’intérieur pour ce code régional et de ce code de pays/région. 
  
Pour plus d’informations sur les cmdlets et Skype Entreprise Server Management Shell, voir la documentation Skype Entreprise Server Management Shell.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Lignes téléphoniques privées dans les déploiements mixtes

Les lignes téléphoniques privées doivent être configurées uniquement pour les déploiements de Skype Entreprise Server ou Lync Server 2013. Dans un déploiement dans lequel des serveurs exécutent des versions antérieures de Lync Server, lorsqu’un utilisateur d’une version antérieure tente d’appeler une ligne téléphonique privée, le routage de l’appel échoue car le serveur ne peut pas effectuer de recherche de numéro inversée sur une ligne téléphonique privée.
  


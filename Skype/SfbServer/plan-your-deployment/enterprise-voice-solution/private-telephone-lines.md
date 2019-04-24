---
title: Planifier des lignes téléphoniques privées avec Skype pour les entreprises
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planification des lignes (secondaire) privées dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 16c5b6e29041280bf92f849bd327d864c7b58e15
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206535"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planifier des lignes téléphoniques privées avec Skype pour les entreprises
 
Planification des lignes (secondaire) privées dans Skype pour Business Server Enterprise Voice.
  
Skype pour Business Server vous permet de donner aux utilisateurs une ligne de téléphone privé en plus de la ligne de leur numéro de téléphone principal. Les lignes téléphoniques privées sont souvent attribuées aux cadres et aux personnes qui souhaitent un numéro de téléphone non répertorié auquel ils peuvent être joints directement.
  
Lignes téléphoniques privées peuvent uniquement être configurés avec la Skype pour Business Server Management Shell. Vous ne pouvez pas configurer les lignes téléphoniques privées avec la Skype pour le panneau de configuration serveur Business. Lignes téléphoniques privées doivent être configurés uniquement dans les déploiements de Skype pour Business Server et non pas dans des déploiements mixtes.
  
## <a name="characteristics-of-private-telephone-lines"></a>Caractéristiques des lignes téléphoniques privées

Bien que le concept d’une ligne téléphonique privé est fondamentalement simple, il est important de comprendre les caractéristiques des lignes privées et les moyens dans lequel elles sont similaires aux et différent de lignes de numéro de téléphone principal des utilisateurs.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Caractéristiques générales des lignes téléphoniques privées

- Un utilisateur ne peut disposer que d’une seule ligne téléphonique privée.
    
- Un utilisateur avec une ligne téléphonique privée n’est doté que d’une seule messagerie vocale et reçoit des notifications d’appel en absence à une adresse de messagerie unique.
    
- Un utilisateur avec une ligne téléphonique privée ne dispose pas d’une deuxième adresse SIP, et une deuxième ligne téléphonique privée n’accorde pas à l’utilisateur une deuxième présence sur le réseau (comme une deuxième identité de messagerie instantanée). 
    
- Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux. Ils ne sont pas disponibles avec les déploiements hébergés de Skype pour Business Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Différences entre les lignes téléphoniques privées et principales

- Les numéros de téléphone des lignes privées ne s’affichent pas dans les annuaires ou les listes de contacts dérivés des services de domaine Active Directory.
    
- Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, sonnerie d’appel d’équipe, prise d’appel de groupe et application Response Group.
    
- Les appels sur une ligne téléphonique privée présentent une sonnerie spéciale et la notification système de l’appel indique à l’utilisateur que l’appel entre sur sa ligne privée.
    
- Les appels sur la ligne téléphonique privée sonnent systématiquement. Ils ne suivent pas les règles « Ne pas déranger ».
    
- Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour passer des appels sortants. Lorsqu’un utilisateur avec une ligne téléphonique privée effectue un appel, l’appel provient d’une ligne téléphonique principale de l’utilisateur et ne masque pas le nom d’utilisateur ou le numéro de téléphone principal de l’utilisateur de la personne appelée.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre les lignes téléphoniques privées et principales

- Les appels sans réponse sur une ligne téléphonique privée sont routés vers la même boîte de réception vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).
    
- Le parcage d’appel et la prise d’appel fonctionnent avec les lignes téléphoniques privées exactement la même manière qu’avec la ligne téléphonique principale de l’utilisateur.
    
- Lors de la sonnerie simultanée est activée sur la ligne du numéro de téléphone principal d’un utilisateur, il est également activé sur la ligne téléphonique privée.
    
- Le numéro de téléphone pour une ligne téléphonique privée est enregistré dans l’enregistrement des détails des appels de la même manière que le numéro de téléphone de ligne de numéro de téléphone principal d’un utilisateur, mais en indiquant qu’il est un numéro de téléphone privé.
    
- Après qu’un utilisateur réponses qu'un appel sur une ligne téléphonique privée, l’appel est traitée comme un appel sur la ligne téléphonique principale de l’utilisateur. Par exemple, si un utilisateur reçoit un appel sur une ligne téléphonique privée transfère l’appel ou invite d’autres personnes à une téléconférence, le nom d’utilisateur apparaît dans Skype pour les entreprises et le numéro de téléphone de la ligne téléphonique principale de l’utilisateur s’affiche dans l’appelant ID.
    
- Un utilisateur peut rediriger un appel (vers une autre destination, comme un téléphone mobile ou personnel, avant de répondre) provenant de la ligne téléphonique privée comme avec une ligne téléphonique principale. 
    
    > [!NOTE]
    > Lorsqu’un appel sur la ligne privée est routé sur un autre numéro de téléphone, le numéro de la ligne privée est mis à la disposition de l’autre numéro et peut être affiché dans les journaux pour ce numéro. 
  
    > [!NOTE]
    > Appels d’une conférence à la ligne téléphonique privée n’aura une indication de *ligne privée* dans la notification système entrante.
  
## <a name="administering-private-telephone-lines"></a>Administration des lignes téléphoniques privées

Outre les aspects techniques liés à la création et à la gestion des lignes téléphoniques privées, vous devrez établir des procédures administratives, entre autres déterminer des stratégies afin de définir qui est autorisé à obtenir une ligne privée dans l’organisation, créer et gérer des listes de personnes et de leurs lignes téléphoniques, créer éventuellement un annuaire téléphonique privé pour les cadres, organiser des formations pour les utilisateurs, et ainsi de suite.
  
> [!NOTE]
> La ligne téléphonique privée est stockée dans Active Directory en tant qu’attribut msRTCSIP-PrivateLine de l’objet utilisateur. Par défaut, tout membre du groupe Utilisateurs authentifiés dispose d’un accès en lecture à cet attribut. 
  
### <a name="assigning-telephone-numbers"></a>Attribution de numéros de téléphone

 Comptes pour les nouveaux utilisateurs qui ont besoin de lignes téléphoniques privées sont créés de la même manière que les comptes des lignes téléphoniques privées, à l’aide de Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell.
  
Utilisez l’applet de commande **Set-CsUser** dans le Skype pour Business Server Management Shell pour affecter un numéro de téléphone à une ligne téléphonique privée pour un utilisateur, par exemple, **Set-CsUser-Identity « sip:joe@contoso.com » - PrivateLine « Tel : + 14255551212 »**.
  
Numéros de téléphone des lignes privées peut être comprise entre 3 et 15 chiffres de longueur et doit être précédés du « TEL : » préfixe. Ils peuvent ne pas présenter d’indicatif régional, ni d’indicatif de pays/région si l’organisation dispose d’une sélection directe à l’arrivée pour ces indicatifs. 
  
Pour plus d’informations sur les applets de commande et Skype pour Business Server Management Shell, voir la Skype pour la documentation sur Business Server Management Shell.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Lignes téléphoniques privées dans des déploiements mixtes

Lignes téléphoniques privées doivent être configurés uniquement pour les déploiements de Skype pour Business Server ou Microsoft Lync Server 2013. Dans un déploiement qui contient des serveurs exécutant des versions précédentes de Lync Server, lorsqu’un utilisateur sur une version antérieure tente d’appeler une ligne téléphonique privée, le routage de l’appel échoue car le serveur ne peut pas effectuer une recherche inversée de numéros sur une ligne téléphonique privée.
  


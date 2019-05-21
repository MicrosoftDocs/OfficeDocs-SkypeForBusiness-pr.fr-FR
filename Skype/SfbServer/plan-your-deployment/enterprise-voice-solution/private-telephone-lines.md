---
title: Planifier des lignes téléphoniques privées avec Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planification de lignes téléphoniques privées (secondaires) dans Skype entreprise Server Voice.
ms.openlocfilehash: 38dd81bb0fae9f7edd062e111db462d264dda1d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276559"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Planifier des lignes téléphoniques privées avec Skype entreprise
 
Planification de lignes téléphoniques privées (secondaires) dans Skype entreprise Server Voice.
  
Skype entreprise Server vous permet de donner aux utilisateurs une deuxième ligne téléphonique privée en plus de leur ligne téléphonique principale. Les lignes téléphoniques privées sont souvent attribuées aux cadres et aux personnes qui souhaitent un numéro de téléphone non répertorié auquel ils peuvent être joints directement.
  
Les lignes téléphoniques privées ne peuvent être configurées qu’avec Skype entreprise Server Management Shell. Vous ne pouvez pas configurer de lignes téléphoniques privées avec le panneau de configuration Skype entreprise Server. Les lignes téléphoniques privées doivent être configurées uniquement dans les déploiements de Skype entreprise Server et non dans les déploiements mixtes.
  
## <a name="characteristics-of-private-telephone-lines"></a>Caractéristiques des lignes téléphoniques privées

Même si le concept d’une deuxième ligne téléphonique privée est fondamentalement simple, il est important de bien comprendre les caractéristiques des lignes privées et celles selon lesquelles celles-ci sont similaires et différentes des principales lignes de téléphone de l’utilisateur.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Caractéristiques générales des lignes téléphoniques privées

- Un utilisateur ne peut disposer que d’une seule ligne téléphonique privée.
    
- Un utilisateur avec une ligne téléphonique privée n’est doté que d’une seule messagerie vocale et reçoit des notifications d’appel en absence à une adresse de messagerie unique.
    
- Un utilisateur avec une ligne téléphonique privée ne dispose pas d’une deuxième adresse SIP, et une deuxième ligne téléphonique privée n’accorde pas à l’utilisateur une deuxième présence sur le réseau (comme une deuxième identité de messagerie instantanée). 
    
- Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux. Elles ne sont pas disponibles dans les déploiements hébergés de Skype entreprise Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Différences entre les lignes téléphoniques privées et principales

- Les numéros de téléphone des lignes privées ne s’affichent pas dans les annuaires ou les listes de contacts dérivés des services de domaine Active Directory.
    
- Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, sonnerie d’appel d’équipe, prise d’appel de groupe et application Response Group.
    
- Les appels sur une ligne téléphonique privée présentent une sonnerie spéciale et la notification système de l’appel indique à l’utilisateur que l’appel entre sur sa ligne privée.
    
- Les appels sur la ligne téléphonique privée sonnent systématiquement. Ils ne suivent pas les règles « Ne pas déranger ».
    
- Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour passer des appels sortants. Lorsqu’un utilisateur disposant d’une ligne téléphonique privée effectue un appel, l’appel provient de la ligne téléphonique principale de l’utilisateur et ne masque pas le nom de l’utilisateur ou le numéro de téléphone principal de l’utilisateur de la personne appelée.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Similitudes entre les lignes téléphoniques privées et principales

- Les appels sans réponse sur une ligne téléphonique privée sont routés vers la même boîte de réception vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).
    
- Le parc d’appels et le prélèvement d’appel fonctionnent avec des lignes téléphoniques privées de la même manière que pour la ligne téléphonique principale de l’utilisateur.
    
- Lorsque la sonnerie simultanée est activée sur la ligne téléphonique principale d’un utilisateur, celle-ci est également activée sur la ligne téléphonique privée.
    
- Le numéro de téléphone d’une ligne téléphonique privée est enregistré dans l’enregistrement des détails de l’appel de la même manière que le numéro de téléphone de la ligne téléphonique principale d’un utilisateur, mais il indique qu’il s’agit d’un numéro de téléphone privé.
    
- Lorsque l’utilisateur répond à un appel sur une ligne téléphonique privée, l’appel est traité comme un appel sur la ligne téléphonique principale de l’utilisateur. Par exemple, si un utilisateur qui reçoit un appel sur une ligne téléphonique privée transfère l’appel ou invitez d’autres personnes à participer à une conférence téléphonique, le nom de l’utilisateur apparaît dans Skype entreprise et le numéro de téléphone de la ligne téléphonique principale de l’utilisateur apparaît dans l’identification de l’appelant.
    
- Un utilisateur peut rediriger un appel (vers une autre destination, comme un téléphone mobile ou personnel, avant de répondre) provenant de la ligne téléphonique privée comme avec une ligne téléphonique principale. 
    
    > [!NOTE]
    > Lorsqu’un appel sur la ligne privée est routé sur un autre numéro de téléphone, le numéro de la ligne privée est mis à la disposition de l’autre numéro et peut être affiché dans les journaux pour ce numéro. 
  
    > [!NOTE]
    > Les appels d’une conférence vers la ligne téléphonique privée n’indiquent pas de *ligne privée* dans la notification du système entrant.
  
## <a name="administering-private-telephone-lines"></a>Administration des lignes téléphoniques privées

Outre les aspects techniques liés à la création et à la gestion des lignes téléphoniques privées, vous devrez établir des procédures administratives, entre autres déterminer des stratégies afin de définir qui est autorisé à obtenir une ligne privée dans l’organisation, créer et gérer des listes de personnes et de leurs lignes téléphoniques, créer éventuellement un annuaire téléphonique privé pour les cadres, organiser des formations pour les utilisateurs, et ainsi de suite.
  
> [!NOTE]
> La ligne téléphonique privée est stockée dans Active Directory en tant qu’attribut msRTCSIP-PrivateLine de l’objet utilisateur. Par défaut, tout membre du groupe Utilisateurs authentifiés dispose d’un accès en lecture à cet attribut. 
  
### <a name="assigning-telephone-numbers"></a>Attribution de numéros de téléphone

 Les comptes pour les nouveaux utilisateurs qui ont besoin de lignes téléphoniques privées sont créés de la même manière que les comptes sans lignes téléphoniques privées, en utilisant le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell.
  
Utilisez l’applet de commande **Set-Csuser** dans Skype entreprise Server Management Shell pour affecter un numéro de téléphone à une ligne téléphonique privée pour un utilisateur (par exemple, **Set-Csuser-identity "SIP:joe@contoso.com"-PrivateLine "Tél: + 14255551212"**.
  
Les numéros de téléphone des lignes téléphoniques privées peuvent contenir entre 3 et 15 numéros de longueur et doivent être précédés du préfixe «TEL:». Ils peuvent ne pas présenter d’indicatif régional, ni d’indicatif de pays/région si l’organisation dispose d’une sélection directe à l’arrivée pour ces indicatifs. 
  
Pour plus d’informations sur les applets de applet et Skype entreprise Server Management Shell, voir la documentation de Skype entreprise Server Management Shell.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Lignes téléphoniques privées dans des déploiements mixtes

Les lignes téléphoniques privées doivent être configurées uniquement pour les déploiements de Skype entreprise Server ou Lync Server 2013. Dans le cadre d’un déploiement dans lequel des serveurs exécutent des versions antérieures de Lync Server, quand un utilisateur sur une version antérieure tente d’appeler une ligne téléphonique privée, le routage de l’appel échoue, car le serveur ne peut pas effectuer de recherche inverse sur une ligne téléphonique privée.
  


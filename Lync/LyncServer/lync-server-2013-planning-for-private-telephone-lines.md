﻿---
title: 'Lync Server 2013 : Planification des lignes téléphoniques privées'
TOCTitle: Planification des lignes téléphoniques privées
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412728(v=OCS.15)
ms:contentKeyID: 49298359
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification des lignes téléphoniques privées avec Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-11_

Lync Server 2013 permet d’accorder aux utilisateurs une deuxième ligne téléphonique privée en plus de leur ligne téléphonique principale. Les lignes téléphoniques privées sont souvent attribuées aux cadres et aux personnes qui souhaitent un numéro de téléphone non répertorié auquel ils peuvent être joints directement.

Ces lignes peuvent être configurées uniquement avec Lync Server Management Shell. Vous ne pouvez pas configurer des lignes téléphoniques privées avec le Panneau de configuration Lync Server. Les lignes téléphoniques privées doivent être configurées uniquement dans le cadre de déploiements Lync Server, et non dans le cadre de déploiements mixtes.

## Caractéristiques des lignes téléphoniques privées

Même si le concept de la deuxième ligne téléphonique privée est simple à la base, il est important de comprendre les caractéristiques des lignes privées, ainsi que leurs similitudes et différences par rapport aux lignes téléphoniques principales des utilisateurs.

## Caractéristiques générales des lignes téléphoniques privées

  - Un utilisateur ne peut disposer que d’une seule ligne téléphonique privée.

  - Un utilisateur avec une ligne téléphonique privée n’est doté que d’une seule messagerie vocale et reçoit des notifications d’appel en absence à une adresse de messagerie unique.

  - Un utilisateur avec une ligne téléphonique privée ne dispose pas d’une deuxième adresse SIP, et une deuxième ligne téléphonique privée n’accorde pas à l’utilisateur une deuxième présence sur le réseau (comme une deuxième identité de messagerie instantanée).

  - Les lignes téléphoniques privées sont disponibles uniquement pour les déploiements locaux. Elles ne le sont pas avec des déploiements hébergés de Lync Server.

## Différences entre les lignes téléphoniques privées et principales

  - Les numéros de téléphone des lignes privées ne s’affichent pas dans les annuaires ou les listes de contacts dérivés des services de domaine Active Directory.

  - Aucune des fonctionnalités suivantes n’est disponible avec une ligne téléphonique privée : transfert d’appel, appel d’équipe, délégation, sonnerie d’appel d’équipe, prise d’appel de groupe et application Response Group.

  - Les appels sur une ligne téléphonique privée présentent une sonnerie spéciale et la notification système de l’appel indique à l’utilisateur que l’appel entre sur sa ligne privée.

  - Les appels sur la ligne téléphonique privée sonnent systématiquement. Ils ne suivent pas les règles « Ne pas déranger ».

  - Les lignes téléphoniques privées sont uniquement entrantes et ne peuvent pas être utilisées pour passer des appels sortants. Lorsqu’un utilisateur doté d’une ligne téléphonique privée passe un appel, l’appel provient de la ligne téléphonique principale de l’utilisateur et ne masque pas le nom ou le numéro de téléphone principal de l’utilisateur à la personne appelée.

## Similitudes entre les lignes téléphoniques privées et principales

  - Les appels sans réponse sur une ligne téléphonique privée sont routés vers la même boîte de réception vocale que pour la ligne téléphonique principale (si la messagerie vocale est activée).

  - Le parcage d’appel et la prise d’appel fonctionnent avec les lignes téléphoniques privées exactement de la même manière qu’avec la ligne téléphonique principale de l’utilisateur.

  - Lorsque la sonnerie simultanée est activée sur la ligne téléphonique principale de l’utilisateur, elle l’est également sur la ligne téléphonique privée.

  - Le numéro de téléphone d’une ligne téléphonique privée est consigné dans l’enregistrement des détails des appels comme le numéro de la ligne principale d’un utilisateur, mais en précisant qu’il s’agit d’un numéro de téléphone privé.

  - Une fois que l’utilisateur a répondu à un appel sur la ligne téléphonique privée, l’appel est traité de la même manière qu’un appel passé sur la ligne téléphonique principale d’un utilisateur. Par exemple, si un utilisateur reçoit un appel sur une ligne téléphonique privée et le transfère ou invite d’autres personnes à une téléconférence, son nom est alors affiché dans Lync 2013 et le numéro de téléphone de sa ligne principale s’affiche dans l’identification de l’appelant.

  - Un utilisateur peut rediriger un appel (vers une autre destination, comme un téléphone mobile ou personnel, avant de répondre) provenant de la ligne téléphonique privée comme avec une ligne téléphonique principale.
    
    > [!NOTE]  
    > Lorsqu’un appel sur la ligne privée est routé sur un autre numéro de téléphone, le numéro de la ligne privée est mis à la disposition de l’autre numéro et peut être affiché dans les journaux pour ce numéro.    
    > [!NOTE]  
    > Les appels d’une conférence vers la ligne téléphonique privée ne porteront pas la mention de <em>ligne privée</em> dans la notification système entrante.

## Administration des lignes téléphoniques privées

Outre les aspects techniques liés à la création et à la gestion des lignes téléphoniques privées, vous devrez établir des procédures administratives, entre autres déterminer des stratégies afin de définir qui est autorisé à obtenir une ligne privée dans l’organisation, créer et gérer des listes de personnes et de leurs lignes téléphoniques, créer éventuellement un annuaire téléphonique privé pour les cadres, organiser des formations pour les utilisateurs, et ainsi de suite.

> [!NOTE]  
> La ligne téléphonique privée est stockée dans Active Directory en tant qu’attribut msRTCSIP-PrivateLine de l’objet utilisateur. Par défaut, tout membre du groupe Utilisateurs authentifiés dispose d’un accès en lecture à cet attribut.

## Attribution de numéros de téléphone

Les comptes des nouveaux utilisateurs, qui ont besoin de lignes téléphoniques privées, sont créés de la même manière que les comptes dans lignes privées à l’aide du Panneau de configuration Lync Server ou de Lync Server Management Shell.

Utilisez l’applet de commande **Set-CsUser** dans Lync Server Management Shell pour attribuer à un utilisateur un numéro de téléphone de ligne privée, par exemple, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"** .

Les numéros de téléphone des lignes téléphoniques privées peuvent comporter entre 3 et 15 chiffres et doivent être précédés du préfixe « TEL: ». Ils peuvent ne pas présenter d’indicatif régional, ni d’indicatif de pays/région si l’organisation dispose d’une sélection directe à l’arrivée pour ces indicatifs.

Pour plus d’informations sur les applets de commande et Lync Server Management Shell, reportez-vous à la documentation [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Lignes téléphoniques privées dans des déploiements mixtes

Les lignes téléphoniques privées doivent être configurées uniquement pour les déploiements de Lync Server. Dans un déploiement dans lequel il existe à la fois des serveurs Lync Server et Office Communications Server 2007 ou Office Communications Server 2007 R2, si un utilisateur d’une version antérieure tente d’appeler une ligne téléphonique privée, le routage de l’appel échoue car le serveur ne peut pas effectuer de recherche de numéro inversée sur une ligne téléphonique privée.


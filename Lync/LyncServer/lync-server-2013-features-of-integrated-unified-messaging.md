---
title: 'Lync Server 2013 : Fonctionnalités de la messagerie unifiée intégrée'
TOCTitle: Fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398144(v=OCS.15)
ms:contentKeyID: 49296195
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fonctionnalités de la messagerie unifiée intégrée et de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans Lync Server 2013, Voix Entreprise utilise l’infrastructure de la messagerie unifiée Exchange pour offrir les services de répondeur automatique, de notification d’appel, d’accès vocal (dont la messagerie vocale) et de standard automatique.

## Répondeur automatique

La fonction de répondeur automatique consiste à prendre les messages vocaux pour le compte d’utilisateurs qui ne peuvent pas répondre aux appels ou qui sont déjà au téléphone. Elle comprend la lecture d’un message d’accueil personnel, l’enregistrement d’un message et l’envoi du message dans la file d’attente avant d’être finalement remis à la boîte aux lettres de l’utilisateur, qui est stockée sur le serveur de boîte aux lettres Exchange.

Si un appelant laisse un message, celui-ci est transmis à la boîte de réception de l’utilisateur. Si un appelant choisit de ne pas laisser de message, une notification d’appel manqué est stockée dans la boîte aux lettres de l’utilisateur. L’utilisateur peut ensuite accéder à sa boîte de réception à l’aide du client de messagerie et de collaboration de Microsoft Outlook, d’Outlook Web Access, de la technologie Exchange ActiveSync ou d’Outlook Voice Access. L’objet et la priorité des appels peuvent être affichés à peu près de la même façon que dans un message électronique.

## Outlook Voice Access

Outlook Voice Access permet à un utilisateur de Voix Entreprise d’accéder non seulement à la messagerie vocale, mais également à la boîte de réception Exchange, dont à la messagerie électronique, au calendrier et aux contacts à partir d’une interface de téléphonie. Le numéro d’accès d’abonné est attribué par un administrateur de messagerie unifiée Exchange.

## Standard automatique

Le standard automatique est une fonctionnalité de la messagerie unifiée Exchange qui permet de configurer un numéro de téléphone que les utilisateurs extérieurs peuvent composer pour contacter les représentants de la société. Il fournit en particulier une série d’instructions vocales qui aident un appelant externe à naviguer dans un système de menus. La liste des options disponibles est configurée sur le serveur de messagerie unifiée Exchange par l’administrateur de messagerie unifiée Exchange.

## Services de télécopie

messagerie unifiée Exchange inclut des fonctionnalités de télécopie, qui permettent aux utilisateurs de recevoir des télécopies entrantes dans leur boîte aux lettres Exchanged. Pour plus d’informations, reportez-vous à « Messagerie unifiée » dans la documentation Microsoft Exchange Server à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).

> [!NOTE]  
> Les services de télécopie fournis par le serveur de messagerie unifiée Exchange ne sont pas disponibles dans les déploiements de Lync Server intégrés à Microsoft Exchange Server 2010 ou à Exchange 2010 avec le dernier service pack, ou à Exchange 2013.

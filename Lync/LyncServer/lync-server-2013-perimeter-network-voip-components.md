---
title: 'Lync Server 2013 : Composants VoIP du réseau de périmètre'
TOCTitle: Composants VoIP du réseau de périmètre
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398559(v=OCS.15)
ms:contentKeyID: 49297732
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants VoIP du réseau de périmètre dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Les appelants extérieurs qui utilisent des clients de communications unifiées pour des appels individuels ou téléconférences comptent sur le serveur Edge pour les communications vocales avec des collaborateurs.

Sur un serveur Edge, le service Edge d’accès fournit une signalisation SIP pour les appels provenant des utilisateurs Lync qui se situent à l’extérieur du pare-feu de l’organisation. Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu. Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.

Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.


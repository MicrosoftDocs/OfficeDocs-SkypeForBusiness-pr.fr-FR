---
title: URL et plages d'adresses IP Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: Découvrez comment configurer des URL et plages d'adresses IP Office 365, contourner le proxy de transfert lorsque cela est possible pour les connexions au service Microsoft Teams, et les conditions requises pour les stratégies de mise en réseau et de sécurité.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f946bc45fae230c0fd0ead9c06d0ced537bc7f92
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2018
ms.locfileid: "18998972"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL et plages d'adresses IP Office 365
=====================================

Accédez à [Office 365 URL et plages d’adresses IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) pour une liste détaillée et mise à jour de l’URL, adresses, ports, protocoles IP et qui doivent être correctement configurés pour les équipes. Microsoft améliore en permanence le service Office 365 et ajouter de nouvelles fonctionnalités, ce qui signifie que les ports requis, URL, et adresses IP peuvent changer au fil du temps. Il est recommandé [vous abonner via le flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque cette information est mis à jour ou modifiée.

Les équipes expérience d’appel et de réunions s’appuie sur le prochaine génération basée sur le cloud infrastructure qui est également utilisé par Skype et Skype pour les entreprises. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité. De ce fait, il existe des URL et adresses IP qui sont requis qui peut éventuellement être associée à la fois Skype et Skype pour les entreprises.

Pour toutes les charges de travail Office 365, la méthode recommandée de connexion aux services d’équipes ignore le proxy de transfert lorsque cela est possible. Lorsqu’un serveur proxy se trouve entre un client et les centres de données Office 365, média peut être forcée sur TCP au lieu de UDP, ce qui aurait un impact sur la qualité des médias. Télécharger les fichiers PAC exemple proxy qui peuvent être utilisés pour configurer le trafic de contournement de média à partir de [points de terminaison de gestion Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si vos stratégies de sécurité et de réseau requièrent Office 365 le trafic passe par un serveur proxy, assurez-vous que les conditions ci-dessus sont remplies avant de déployer des équipes en production (passez en revue les [Serveurs Proxy pour Skype pour Business Online](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) conseils).

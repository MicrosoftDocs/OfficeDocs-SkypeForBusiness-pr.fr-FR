---
title: URL et plages d'adresses IP Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: Découvrez comment configurer des URL et plages d'adresses IP Office 365, contourner le proxy de transfert lorsque cela est possible pour les connexions au service Microsoft Teams, et les conditions requises pour les stratégies de mise en réseau et de sécurité.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 713815836b2edcad31528abc01c74a2332ecf88a
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL et plages d'adresses IP Office 365
=====================================

Pour obtenir une liste détaillée et actualisée de l’URL, adresses, ports, protocoles IP et qui doivent être correctement configurés pour les équipes, accédez à [Office 365 URL et les plages d’adresses IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) . Microsoft améliore en permanence le service Office 365 et ajouter de nouvelles fonctionnalités, qui signifie que les ports requis, URL, et les adresses IP changent au fil du temps. Il est recommandé que vous vous [abonnez-vous via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque cette information est mise à jour ou modifiée.

Les équipes d’expérience de réunions et d’appel repose sur la prochaine nuage infrastructure de génération qui est également utilisé par Skype et Skype pour les entreprises. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité. En tant que tel, URL et adresses IP qui sont requis qui peut éventuellement être associés à la fois Skype et Skype pour les entreprises.

Pour toutes les charges de travail Office 365, la méthode recommandée de connexion aux services d’équipes ignore le proxy transférer lorsque cela est possible. Lorsqu’un serveur proxy se trouve entre un client et les centres de données d’Office 365, media peut être forcée sur TCP au lieu de UDP, ce qui affecterait la qualité du support. Télécharger les fichiers PAC exemple proxy qui peuvent être utilisés pour configurer le contournement du trafic à partir de [points de terminaison de gestion d’Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si vos stratégies de sécurité et de réseau nécessitent le trafic Office 365 via un serveur proxy, assurez-vous que les conditions ci-dessus sont remplies avant de déployer des équipes en production (consulter la section [Serveurs Proxy pour Skype pour l’activité en ligne](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) pour conseils).

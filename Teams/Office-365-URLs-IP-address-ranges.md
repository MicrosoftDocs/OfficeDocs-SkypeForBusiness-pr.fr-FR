---
title: URL et plages d'adresses IP Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Découvrez comment configurer des URL et plages d'adresses IP Office 365, contourner le proxy de transfert lorsque cela est possible pour les connexions au service Microsoft Teams, et les conditions requises pour les stratégies de mise en réseau et de sécurité.
localization_priority: Normal
search.appverid: MET150
f1.keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ccecd9faf9bb023ba80c01783c24a95c44e586f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695669"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL et plages d'adresses IP Office 365
=====================================

Accédez à l’article [Plages d'adresses URL et IP d’Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour obtenir la liste détaillée et actualisée des URL, adresses IP, ports et protocoles qui doivent être configurés correctement dans Teams. Microsoft améliore en permanence le service Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps. Nous vous recommandons de [vous abonner via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.

L'expérience d'appels et de réunions Teams est basée sur l'infrastructure cloud de nouvelle génération, qui est également utilisée par Skype et Skype Entreprise. Ces investissements technologiques incluent les services Cloud Azure pour le traitement et le signalement des contenus multimédias, le codec vidéo H. 264, le codec audio de soie et opus, la résilience réseau, la télémétrie et les diagnostics qualité. Par conséquent, des adresses URL et IP sont requises qui peuvent être associées à Skype et Skype Entreprise.

Pour toutes les charges de travail Office 365, la méthode de connexion aux services Teams recommandée consiste à contourner le proxy de transfert lorsque cela est possible. Lorsqu’un serveur proxy est situé entre un client et les centres de données Office 365, le média peut être forcé sur TCP au lieu d’UDP, ce qui aurait une incidence sur la qualité du média. Téléchargez les fichiers PAC de modèle de proxy qui peuvent être utilisés pour configurer le contournement du trafic dans [Gestion des points de terminaison Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si votre réseau et vos stratégies de sécurité nécessitent le trafic d’Office 365 pour circuler par le biais d’un serveur proxy, assurez-vous que les exigences ci-dessus sont déjà satisfaites avant de déployer des équipes en production (révisez les [serveurs proxy pour teams ou Skype entreprise Online](proxy-servers-for-skype-for-business-online.md) pour obtenir des conseils).

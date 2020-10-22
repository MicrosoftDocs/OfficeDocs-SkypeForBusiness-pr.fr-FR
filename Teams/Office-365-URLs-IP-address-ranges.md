---
title: URL et plages d’adresses IP de Microsoft 365 et Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Apprenez à configurer correctement les URL et plages d’adresses IP de Microsoft 365 ou d’Office 365 et à ignorer le proxy de transfert dans la mesure du possible pour les connexions au service Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ad3ffdfd47b67ce21fb7f47a911afa67159f3e7
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650817"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL et plages d’adresses IP de Microsoft 365 et Office 365
=======================================================

Accédez aux [URL et plages d’adresses IP de Microsoft 365 et Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour obtenir une liste détaillée et à jour des URL, adresses IP, ports et protocoles qui doivent être correctement configurés pour les équipes. Microsoft améliore en permanence les services Microsoft 365 et Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps. Nous vous recommandons de [vous abonner via RSS](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.

L'expérience d'appels et de réunions Teams est basée sur l'infrastructure cloud de nouvelle génération, qui est également utilisée par Skype et Skype Entreprise. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité. Par conséquent, des adresses URL et IP sont requises qui peuvent être associées à Skype et Skype Entreprise.

Pour toutes les charges de travail Microsoft 365 et Office 365, la méthode de connexion recommandée aux services d’équipe ignore le proxy de transfert, dans la mesure du possible. Lorsqu’un serveur proxy est situé entre un client et les centres de données Office 365, le média peut être forcé sur TCP au lieu d’UDP, ce qui aurait une incidence sur la qualité du média. Téléchargez des exemples de fichiers PAC de proxy qui peuvent être utilisés pour configurer le contournement du trafic à partir de la [gestion des points de terminaison Microsoft 365 et Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).

Si votre réseau et vos stratégies de sécurité nécessitent le trafic Microsoft 365 ou Office 365 pour passer par le biais d’un serveur proxy, assurez-vous que les exigences ci-dessus sont déjà satisfaites avant de déployer teams en production. Pour plus d’informations, voir [serveurs proxy pour teams ou Skype entreprise Online](proxy-servers-for-skype-for-business-online.md).

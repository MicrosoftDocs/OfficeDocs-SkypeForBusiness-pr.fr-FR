---
title: URL et plages d’adresses IP Microsoft 365 et Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Découvrez comment configurer correctement les URL et plages d’adresses IP Microsoft 365 ou Office 365, et ignorer le proxy lorsque cela est possible pour les connexions au service Microsoft Teams.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094516"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL et plages d’adresses IP Microsoft 365 et Office 365
=======================================================

Allez aux URL et [plages d’adresses IP Microsoft 365 et Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour obtenir une liste détaillée et à jour des URL, adresses IP, ports et protocoles qui doivent être correctement configurés pour Teams. Microsoft améliore en permanence les services Microsoft 365 et Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps. Nous vous recommandons de vous [abonner via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.

L’expérience d’appels et de réunions Teams est basée sur l’infrastructure cloud nouvelle génération qui est également utilisée par Skype et Skype Entreprise. Ces investissements technologiques incluent les services cloud Azure pour le traitement et la signalisation multimédia, le codec vidéo H.264, SILK et Service audio codec, la résilience réseau, la télémétrie et les diagnostics de qualité. Ainsi, certaines URL et adresses IP requises peuvent être associées à Skype et à Skype Entreprise.

Pour toutes les charges de travail Microsoft 365 et Office 365, la méthode de connexion recommandée aux services Teams ignore le proxy de substitution, si possible. Lorsqu’un serveur proxy se trouve entre un client et les centres de données Office 365, les médias peuvent être forcés sur TCP au lieu d’UDP, ce qui a une incidence sur la qualité du média. Téléchargez des exemples de fichiers PAC proxy qui peuvent être utilisés pour configurer la dérivation pour le trafic à partir de la gestion des points de terminaison [Microsoft 365 et Office 365.](/office365/enterprise/managing-office-365-endpoints)

Si vos stratégies de réseau et de sécurité nécessitent que le trafic de Microsoft 365 ou d’Office 365 passe par un serveur proxy, assurez-vous que les conditions ci-dessus sont déjà remplies avant de déployer Teams en production. Pour plus d’informations, [lisez Serveurs proxy pour Teams ou Skype Entreprise Online.](proxy-servers-for-skype-for-business-online.md)
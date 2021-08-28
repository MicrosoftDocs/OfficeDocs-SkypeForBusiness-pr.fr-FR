---
title: Microsoft 365 url Office 365 et des plages d’adresses IP
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Découvrez comment configurer correctement les URL Microsoft 365 ou Office 365 et les plages d’adresses IP, et ignorer le proxy de serveur proxy lorsque c’est possible pour les connexions Microsoft Teams service.
ms.localizationpriority: medium
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
ms.openlocfilehash: ebbac20f7306aa5014aa5703a57813e3c631a9d3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601219"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 url Office 365 et des plages d’adresses IP

Pour obtenir une liste détaillée et à jour des URL, adresses IP, ports et protocoles qui doivent être correctement configurés pour Teams, allez aux URL et [plages](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) d’adresses IP Microsoft 365 et Office 365. Microsoft améliore en permanence les services Microsoft 365 et Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps. Nous vous recommandons de vous abonner [via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.

L Teams d’appels et de réunions est basée sur l’infrastructure cloud nouvelle génération utilisée par les utilisateurs de Skype et Skype Entreprise. Ces investissements technologiques incluent les services cloud Azure pour le traitement des médias et la signalisation, le codec vidéo H.264, SILK et Service audio codec, la résilience réseau, la télémétrie et les diagnostics de qualité. Ainsi, certaines URL et adresses IP requises peuvent être associées à des adresses Skype et Skype Entreprise.

Pour toutes les Microsoft 365 et Office 365 charges de travail, la méthode de connexion recommandée pour Teams services est d’ignorer le proxy de substitution si possible. Lorsqu’un serveur proxy se trouve entre un client et les centres de données Office 365, les médias peuvent être forcés sur TCP au lieu d’UDP, ce qui a une incidence sur la qualité des médias. Téléchargez des exemples de fichiers PAC proxy qui peuvent être utilisés pour configurer la dérivation pour le trafic à partir de la gestion Microsoft 365 et [Office 365 points de terminaison.](/office365/enterprise/managing-office-365-endpoints)

Si vos stratégies de réseau et de sécurité nécessitent que le trafic Microsoft 365 ou Office 365 passe par un serveur proxy, assurez-vous que les exigences ci-dessus sont déjà remplies avant de déployer Teams en production. Pour plus d’informations, [lisez Serveurs proxy pour Teams ou Skype Entreprise Online.](proxy-servers-for-skype-for-business-online.md)
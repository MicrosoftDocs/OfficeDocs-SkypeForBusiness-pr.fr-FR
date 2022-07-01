---
title: URL et plages d’adresses IP Microsoft 365 et Office 365
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Découvrez comment configurer correctement Microsoft 365 ou Office 365 URL et plages d’adresses IP et contourner le proxy de transfert lorsque cela est possible pour les connexions avec le service Microsoft Teams.
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
ms.openlocfilehash: e2f638b9fb29c80806082e02f2d0b09ceec619d0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563732"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URL et plages d’adresses IP Microsoft 365 et Office 365

Accédez à [Microsoft 365 et Office 365 URL et plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour obtenir une liste détaillée et à jour des URL, adresses IP, ports et protocoles qui doivent être correctement configurés pour Teams. Microsoft améliore en permanence les services Microsoft 365 et Office 365 et ajoute de nouvelles fonctionnalités, ce que signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps. Nous vous recommandons de vous [abonner via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées.

L’expérience d’appels et de réunions Teams repose sur l’infrastructure cloud de nouvelle génération qui est également utilisée par Skype et Skype Entreprise. Ces investissements technologiques incluent les services cloud basés sur Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et les diagnostics de qualité. Par conséquent, il existe des URL et des adresses IP requises qui peuvent être associées à Skype et à Skype Entreprise.

Pour toutes les charges de travail Microsoft 365 et Office 365, la méthode de connexion recommandée aux services Teams contourne le proxy de transfert si possible. Lorsqu’un serveur proxy se trouve entre un client et les centres de données Office 365, le média peut être forcé sur TCP au lieu d’UDP, ce qui aurait un impact sur la qualité du média. Téléchargez des exemples de fichiers PAC de proxy qui peuvent être utilisés pour configurer le contournement du trafic à partir de la gestion des points de terminaison [Microsoft 365 et Office 365](/office365/enterprise/managing-office-365-endpoints).

Si vos stratégies de mise en réseau et de sécurité nécessitent que Microsoft 365 ou Office 365 le trafic transite par un serveur proxy, assurez-vous que les exigences ci-dessus sont déjà remplies avant de déployer Teams en production. Pour plus d’informations, consultez [Serveurs proxy pour Teams ou Skype Entreprise Online](proxy-servers-for-skype-for-business-online.md).
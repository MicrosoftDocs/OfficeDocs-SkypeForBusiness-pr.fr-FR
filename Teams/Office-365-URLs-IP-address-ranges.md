---
title: URL et plages d'adresses IP Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Découvrez comment configurer des URL et plages d'adresses IP Office 365, contourner le proxy de transfert lorsque cela est possible pour les connexions au service Microsoft Teams, et les conditions requises pour les stratégies de mise en réseau et de sécurité.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9673d25234f4dfa8d28259701a18739c5307ee9
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2019
ms.locfileid: "29593917"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL et plages d'adresses IP Office 365
=====================================

Accédez à [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) pour une liste détaillée et mise à jour de l’URL, adresses, ports, protocoles IP et qui doivent être correctement configurés pour les équipes. Microsoft améliore en permanence le service Office 365 et ajouter de nouvelles fonctionnalités, ce qui signifie que les ports requis, URL, et adresses IP peuvent changer au fil du temps. Il est recommandé [vous abonner via le flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque cette information est mis à jour ou modifiée.

Les équipes expérience d’appel et de réunions s’appuie sur le prochaine génération basée sur le cloud infrastructure qui est également utilisé par Skype et Skype pour les entreprises. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité. De ce fait, il existe des URL et adresses IP qui sont requis qui peut éventuellement être associée à la fois Skype et Skype pour les entreprises.

Pour toutes les charges de travail Office 365, la méthode recommandée de connexion aux services d’équipes ignore le proxy de transfert lorsque cela est possible. Lorsqu’un serveur proxy se trouve entre un client et les centres de données Office 365, média peut être forcée sur TCP au lieu de UDP, ce qui aurait un impact sur la qualité des médias. Télécharger les fichiers PAC exemple proxy qui peuvent être utilisés pour configurer le trafic de contournement de média à partir de [points de terminaison de gestion Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si vos stratégies de sécurité et de réseau requièrent Office 365 le trafic passe par un serveur proxy, assurez-vous que les conditions ci-dessus sont remplies avant de déployer des équipes en production (passez en revue les [Serveurs Proxy pour Skype pour Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) conseils).

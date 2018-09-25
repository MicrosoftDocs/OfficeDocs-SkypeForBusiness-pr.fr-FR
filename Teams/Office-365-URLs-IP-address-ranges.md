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
ms.openlocfilehash: 228376fb8cbfe65ba9b7c34a659489bad0f09116
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011936"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL et plages d'adresses IP Office 365
=====================================

Accédez à [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) pour une liste détaillée et mise à jour de l’URL, adresses, ports, protocoles IP et qui doivent être correctement configurés pour les équipes. Microsoft améliore en permanence le service Office 365 et ajouter de nouvelles fonctionnalités, ce qui signifie que les ports requis, URL, et adresses IP peuvent changer au fil du temps. Il est recommandé [vous abonner via le flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque cette information est mis à jour ou modifiée.

Les équipes expérience d’appel et de réunions s’appuie sur le prochaine génération basée sur le cloud infrastructure qui est également utilisé par Skype et Skype pour les entreprises. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité. De ce fait, il existe des URL et adresses IP qui sont requis qui peut éventuellement être associée à la fois Skype et Skype pour les entreprises.

Pour toutes les charges de travail Office 365, la méthode recommandée de connexion aux services d’équipes ignore le proxy de transfert lorsque cela est possible. Lorsqu’un serveur proxy se trouve entre un client et les centres de données Office 365, média peut être forcée sur TCP au lieu de UDP, ce qui aurait un impact sur la qualité des médias. Télécharger les fichiers PAC exemple proxy qui peuvent être utilisés pour configurer le trafic de contournement de média à partir de [points de terminaison de gestion Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si vos stratégies de mise en réseau et de sécurité requièrent l'acheminement du trafic Office 365 via un serveur proxy, assurez-vous que les conditions mentionnées plus haut sont satisfaites avant de déployer Teams dans l'environnement de production (consultez l'article [Serveurs proxy pour Skype Entreprise Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) pour plus d'informations.)

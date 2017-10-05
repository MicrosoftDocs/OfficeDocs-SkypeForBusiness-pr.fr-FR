---
title: "URL et plages d'adresses IP Office 365 | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment configurer des URL et plages d'adresses IP Office 365, contourner le proxy de transfert lorsque cela est possible pour les connexions au service Microsoft Teams, et les conditions requises pour les stratégies de mise en réseau et de sécurité."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a226a2d541119c61a3538c86f3502defb739147d
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2017
---
<a name="office-365-urls-and-ip-address-ranges"></a>URL et plages d'adresses IP Office 365
=====================================

Consultez le lien suivant pour obtenir une liste détaillée et actualisée des adresses IP et des ports qui doivent être correctement configurés : [URL et plages d'adresses IP Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US). Microsoft améliore en permanence le service Office 365 et ajoute de nouvelles fonctionnalités ; c'est pourquoi les ports, les URL et adresses IP requis peuvent changer au fil du temps. Consultez le guide [URL et plages d'adresses IP Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) pour obtenir les dernières versions des ports et protocoles. Il est également vivement recommandé de [vous abonner aux flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) pour recevoir des notifications lorsque des points de terminaison sont mis à jour ou modifiés.

Comme mentionné précédemment, l'expérience d'appels et de réunions Microsoft Teams est basée sur l'infrastructure cloud de nouvelle génération, également utilisée par Skype et Skype Entreprise. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité. Dans ce sens, des URL et adresses IP requises peuvent être associées à la fois à Skype et Skype Entreprise.

Pour toutes les charges de travail Office 365, la méthode de connexion recommandée pour les services Microsoft Teams consiste à contourner le proxy de transfert chaque fois que possible. Lorsqu'un serveur proxy est placé entre un client et les centres de données Office 365, les médias peuvent être obligés d'utiliser le protocole TCP au lieu du protocole UDP, ce qui affecterait la qualité multimédia. Vous pouvez télécharger des exemples de fichier de proxy PAC pour configurer le contournement du trafic à partir du guide [Gestion des points de terminaison Office 365](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Si vos stratégies de mise en réseau et de sécurité requièrent l'acheminement du trafic Office 365 via un serveur proxy, assurez-vous que les conditions mentionnées plus haut sont satisfaites avant de déployer Microsoft Teams dans l'environnement de production (Consultez l'article [Serveurs proxy pour Skype Entreprise Online](https://support.office.com/en-us/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) pour plus d'informations.)

---
title: Définir la jonction racine d’une nouvelle passerelle IP ou PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
description: 'Vous devez définir le Trunk racine pour le réseau téléphonique commuté (PSTN) ou IP commuté (RTC) en configurant les éléments suivants :'
ms.openlocfilehash: 8d20fbe13a0530095679fb1f26676ef805f9b189
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684807"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a>Définir la jonction racine d’une nouvelle passerelle IP ou PSTN

Vous devez définir le Trunk racine pour le réseau téléphonique commuté (PSTN) ou IP commuté (RTC) en configurant les éléments suivants :

- **Nom du Trunk**: définissez le nom de domaine complet associé au Trunk.

- **Port d’écoute pour la passerelle IP/PSTN**: définir le port sur lequel va écouter ce Trunk

- **Protocole de transport SIP**: effectuez une sélection dans la liste **TCP** ou **TLS**en fonction de la configuration requise de Trunk.

- **Serveur de médiation associé**: sélectionnez dans la liste des serveurs de médiation disponibles dans votre déploiement

- **Port du serveur de médiation associé**: définir le port sur lequel le serveur de médiation sélectionné écoute

## <a name="see-also"></a>Voir aussi

[Configuration d’une jonction avec déviation du trafic multimédia dans Skype Entreprise Server 2015](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[Configuration d’une jonction sans déviation du trafic multimédia dans Skype Entreprise Server 2015](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[Prise en charge du trunking SIP](https://technet.microsoft.com/library/e3042831-e8d8-4ea2-baa2-1a697401ffa0.aspx)

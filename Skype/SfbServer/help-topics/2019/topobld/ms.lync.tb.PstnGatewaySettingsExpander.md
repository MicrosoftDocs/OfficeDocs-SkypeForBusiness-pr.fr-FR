---
title: Expanseur des paramètres de la passerelle PSTN
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour modifier les paramètres d’une passerelle réseau téléphonique commuté (RTC), modifiez les champs suivants :'
ms.openlocfilehash: 45b3945a811a2e9c9b5d1c0cce805c78368c9a70
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888237"
---
# <a name="pstn-gateway-settings-expander"></a>Expanseur des paramètres de la passerelle PSTN
 
Pour modifier les paramètres d’une passerelle réseau téléphonique commuté (RTC), modifiez les champs suivants :
  
Le nom de domaine complet (FQDN) ou l’adresse IP de la passerelle doit être renseigné. Il détermine si le **nom de domaine complet (FQDN)** de la passerelle du réseau téléphonique commuté (RTC) est défini par l’enregistrement d’hôte DNS (A), une entrée de fichier HÔTE statique ou par l’adresse IP de la passerelle RTC.
  
Le protocole de transport SIP est le protocole  TCP (Transmission Control Protocol) ou le protocole TLS (Transport Layer Security). Le protocole TLS est le protocole par défaut. Pour connaître la prise en charge de la passerelle, reportez-vous à la documentation du fournisseur. Le protocole par défaut, le protocole TLS, est un choix plus sécurisé si la passerelle le prend en charge.
  
Choisissez d’activer IPv4 et IPv6 pour la passerelle.
  
L' **adresse IP média de remplacement** est une définition pour le serveur de médiation pour lequel la passerelle RTC déployée a une adresse IP différente pour le trafic multimédia à l’adresse IP configurée par défaut, qui est généralement dédié pour le trafic SIP. Si vous définissez ce paramètre, la passerelle RTC prend en charge une interface réseau ou un chemin d’accès aux médias différent. Si cette adresse n’est pas renseignée, la passerelle RTC ne prend pas en charge un autre chemin d’accès des médias.
  


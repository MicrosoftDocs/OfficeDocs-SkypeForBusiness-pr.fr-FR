---
title: Expanseur des paramètres de la passerelle PSTN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Pour éditer les paramètres d’une passerelle réseau téléphonique commuté (PSTN), modifiez les champs suivants :'
ms.openlocfilehash: 63c85e5cb9d08761496ffb94d3b719b4fdb11e52
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615730"
---
# <a name="pstn-gateway-settings-expander"></a>Expandeur des paramètres de la passerelle PSTN
 
Pour éditer les paramètres d’une passerelle réseau téléphonique commuté (PSTN), modifiez les champs suivants :
  
Nom de domaine complet (FQDN) ou l’adresse IP de la passerelle est une entrée requise. Elle détermine si le **Nom de domaine complet (FQDN)** de la passerelle du réseau téléphonique commuté (PSTN) est défini par l’enregistrement DNS hôte (A), une entrée de fichier HÔTE statique, ou par l’adresse IP de la passerelle PSTN.
  
Le protocole de transport SIP est soit TCP (Transmission Control Protocol), soit TLS (Transport Layer Security). TLS est le protocole par défaut. Consultez la documentation du fournisseur de la passerelle pour connaître la prise en charge de la passerelle. TLS, protocole par défaut, représente un choix plus sécurisé si la passerelle le prend en charge.
  
Choisissez d’activer IPv4 et IPv6 pour la passerelle.
  
L’**Adresse IP média de remplacement** définit le serveur de médiation : la passerelle PSTN déployée dispose d’une adresse IP différente pour le trafic multimédia par rapport à l’adresse IP configurée par défaut, généralement dédiée au trafic SIP. Si vous définissez ce paramètre, la passerelle PSTN prend en charge une interface réseau ou un chemin d’accès des médias différent. Si cette adresse n’est pas remplie, la passerelle PSTN ne prend pas en charge un autre chemin d’accès des médias.
  


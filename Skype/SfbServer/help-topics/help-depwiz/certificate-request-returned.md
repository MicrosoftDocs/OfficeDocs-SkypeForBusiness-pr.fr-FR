---
title: Demande de certificat (retournée)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'La page État de la demande de certificat en ligne présente des informations importantes qui résultent de la création réussie et de l’envoi de la demande de certificat en ligne. Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher affecter ce certificat aux utilisations des certificats de Skype entreprise Server est activée. Si vous cliquez sur terminer, le certificat est automatiquement attribué à Lync Server 2013 conformément aux étapes de création de la demande de certificat. Par défaut, le certificat est affecté par défaut:'
ms.openlocfilehash: 61e6ea918fea931251470603e2db0b699234267d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301959"
---
# <a name="certificate-request-returned"></a>Demande de certificat (retournée)
 
La page État de la **demande de certificat en ligne** présente des informations importantes qui résultent de la création réussie et de l’envoi de la demande de certificat en ligne. Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher **affecter ce certificat aux utilisations des certificats de Skype entreprise Server** est activée. Si vous cliquez sur **Terminer**, le certificat est automatiquement attribué à Lync Server 2013 conformément aux étapes de création de la demande de certificat. Par défaut, le certificat est affecté par défaut:
  
- Serveur par défaut de Mutual Transport Layer Security (MTLS)-connexions aux clients et autres serveurs
    
- Services Web internes-client et connexions serveur sur le site des services Web interne pour le protocole TLS/SSL (Transport Layer Security/Secure Sockets Layer)
    
- Services Web externes-client et connexions serveur sur le site des services Web externes pour TLS/SSL
    
Cliquez sur le bouton **afficher les détails du certificat** pour afficher le certificat pour vérifier que les propriétés du certificat vous conviennent et que le certificat est prêt à être appliqué et mis en place sur le serveur.
  
Cliquez sur **Terminer** pour terminer le processus de demande de certificat en ligne. Si vous avez coché la case **affecter ce certificat aux utilisations des certificats de Skype entreprise Server**, le certificat est automatiquement attribué. Si vous avez choisi de désactiver cette case à cocher, vous devez affecter le certificat dans une étape distincte. 
  
> [!IMPORTANT]
> Si le certificat racine de l’autorité de certification émettrice ne se trouve pas dans le magasin d’autorités de certification de confiance de l’ordinateur ou s’il ne se trouve pas dans le magasin approprié, vous verrez le statut de synthèse, comme illustré dans l’image suivante. Vous n’avez pas la possibilité d’attribuer le certificat. Pour finaliser le processus d’attribution de certificats, vous devez importer le certificat racine de l’autorité de certification émettrice et les certificats d’autorité de certification intermédiaires, puis attribuer le certificat en cliquant sur **affecter** dans la page de l’Assistant certificat principal.
  


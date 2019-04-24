---
title: Demande de certificat (retournée)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/1/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'La page État de demande de certificat en ligne vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne. Cette page fournit l’empreinte de certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher attribuer ce certificat Skype pour utilisations de certificat Business Server est sélectionnée. Si vous cliquez sur Terminer, le certificat sera automatiquement assigné à Lync Server 2013 à des fins que vous avez définis dans la procédure de création de la demande de certificat. Par défaut, les besoins le certificat sera attribué sont les suivants :'
ms.openlocfilehash: 61e62216cd582a07b95a51d05033482699ca2f3d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201352"
---
# <a name="certificate-request-returned"></a>Demande de certificat (retournée)
 
La page **État de la demande de certificat en ligne** vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne. Cette page fournit l’empreinte de certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher **attribuer ce certificat Skype pour utilisations de certificat Business Server** est sélectionnée. Si vous cliquez sur **Terminer**, le certificat sera automatiquement assigné à Lync Server 2013 à des fins que vous avez définis dans la procédure de création de la demande de certificat. Par défaut, les besoins le certificat sera attribué sont les suivants :
  
- Serveur par défaut pour MTLS Mutual Transport Layer Security () - connexions vers les clients et autres serveurs
    
- Services Web internes - connexions Client et serveur sur le site Web interne services pour Transport Layer Security/Secure Sockets Layer (SSL/TLS)
    
- Services Web externes - connexions Client et serveur sur le site Web externe services pour TLS/SSL
    
Cliquez sur **Afficher les détails du certificat** pour afficher le certificat pour confirmer que les propriétés du certificat sont correctes, et que le certificat est prêt à être appliquée et mis en service sur le serveur.
  
Cliquez sur **Terminer** pour terminer le processus de demande de certificat en ligne. Si vous avez sélectionné la case à cocher **attribuer ce certificat Skype pour les utilisations de certificat de serveur d’entreprise**, le certificat sera automatiquement assigné. Si vous avez choisi de désactiver cette case à cocher, vous devez assigner le certificat dans une étape distincte. 
  
> [!IMPORTANT]
> Si le certificat racine d’autorité de certification émettrice certification ne figure pas dans le magasin de l’ordinateur autorité de Certification racine de confiance, ou si les certificats d’autorité de certification intermédiaires ne sont pas dans le magasin approprié, vous verrez le statut de synthèse, comme illustré dans l’image suivante. Vous n’avez pas l’option pour assigner le certificat. Pour terminer le processus d’affectation de certificat, vous devez importer le certificat racine Autorité de certification émettrice et les certificats d’autorité de certification intermédiaires et puis assigner le certificat en cliquant sur **affecter** sur la page Assistant Certificat principale.
  


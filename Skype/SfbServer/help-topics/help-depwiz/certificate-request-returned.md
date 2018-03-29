---
title: Demande de certificat (renvoyé)
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
description: 'La page d’état de demande de certificat en ligne vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne. Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher attribuer ce certificat à Skype pour les utilisations de certificats de serveur d’entreprise est sélectionnée. Si vous cliquez sur Terminer, le certificat est automatiquement affecté à Lync Server 2013 pour fins que vous avez définies au cours de la procédure de création de la demande de certificat. Par défaut, les besoins qui recevra le certificat sont :'
ms.openlocfilehash: 392fbdf4cae860152a5ed96e9e347a0c51aa6f70
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-returned"></a>Demande de certificat (renvoyé)
 
La page **Statut de la demande de certificat en ligne** vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne. Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher **attribuer ce certificat à Skype pour les utilisations du certificat Business Server** est sélectionnée. Si vous cliquez sur **Terminer**, le certificat est automatiquement affecté à Lync Server 2013 pour fins que vous avez définies au cours de la procédure de création de la demande de certificat. Par défaut, les besoins qui recevra le certificat sont :
  
- Serveur par défaut pour couche sécurité MTLS (Mutual Transport) - connexions aux clients et autres serveurs
    
- Services Web internes - connexions Client et serveur sur le site Web interne site services de Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Les services Web externes - connexions Client et serveur sur le site Web externe site services pour TLS/SSL.
    
Cliquez sur **Afficher les détails du certificat** pour afficher le certificat pour vérifier que les propriétés du certificat sont correctes et que le certificat est prêt à être appliqué et mis en service sur le serveur.
  
Cliquez sur **Terminer** pour terminer le processus de demande de certificat en ligne. Si vous avez sélectionné la case à cocher **attribuer ce certificat à Skype pour les utilisations du certificat serveur de l’entreprise**, le certificat sera automatiquement assigné. Si vous avez choisi de désactiver cette case à cocher, vous devez attribuer le certificat dans une étape distincte. 
  
> [!IMPORTANT]
> Si le certificat émettrice de certification authority (CA) racine n’est pas dans le magasin de l’ordinateur de l’autorité de Certification racine de confiance, ou si les certificats d’autorité de certification intermédiaires ne sont pas dans le magasin approprié, vous verrez le résumé de l’état, comme illustré dans l’image suivante. Vous n’avez pas de l’option pour attribuer le certificat. Pour terminer le processus d’affectation de certificat, vous devez importer le certificat de racine d’autorité de certification émettrice et tout certificat CA intermédiaire et ensuite affecter le certificat en cliquant sur **affecter** sur la page principale de l’Assistant certificat.
  


---
title: Demande de certificat (retournée)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'La page État de la demande de certificat en ligne vous présente les informations importantes faisant suite à la création et l’émission d’une demande de certificat en ligne. Elle fournit l’empreinte du certificat qui l’identifie de manière unique. Par défaut, la case à cocher Affecter ce certificat Skype Entreprise Server les utilisations des certificats est sélectionnée. Si vous cliquez sur Terminer, le certificat est automatiquement affecté à Skype Entreprise Server aux fins que vous avez définies lors des étapes de création de la demande de certificat. Par défaut, le certificat sera assigné aux fins suivantes :'
ms.openlocfilehash: 7f92c95fa5d1588d7563791dca38da46c550048b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740050"
---
# <a name="certificate-request-returned"></a>Demande de certificat (retournée)
 
La page **État de la demande de certificat en ligne** vous présente les informations importantes faisant suite à la création et l’émission d’une demande de certificat en ligne. Elle fournit l’empreinte du certificat qui l’identifie de manière unique. Par défaut, la case à cocher Affecter ce **certificat Skype Entreprise Server les utilisations** des certificats est sélectionnée. Si vous cliquez **sur Terminer,** le certificat est automatiquement affecté à Skype Entreprise Server aux fins que vous avez définies lors des étapes de création de la demande de certificat. Par défaut, le certificat sera assigné aux fins suivantes :
  
- Serveur par défaut pour MTLS (Mutual Transport Layer Security) : connexions aux clients et autres serveurs
    
- Services Web internes : connexions client et serveur sur le site des services Web internes pour TLS/SSL (Transport Layer Security/Secure Sockets Layer)
    
- Services Web externes : connexions client et serveur sur le site de services Web externes pour TLS/SSL
    
Cliquez sur **Afficher les détails du certificat** pour voir le certificat et confirmer que ses propriétés correspondent à vos souhaits et qu’il est prêt à être appliqué et utilisé sur le serveur.
  
Cliquez sur **Terminer** pour achever le processus de demande de certificat en ligne. Si vous avez cocher la case Affecter ce **certificat Skype Entreprise Server les utilisations** de certificat, le certificat sera automatiquement affecté. Si vous choisissez de ne pas activer cette case à cocher, vous devez assigner le certificat lors d’une étape différente. 
  
> [!IMPORTANT]
> Si le certificat racine de l’autorité de certification émettrice ne se trouve pas dans le magasin de l’autorité de certification racine de confiance de l’ordinateur, ou si les certificats d’autorité de certification intermédiaires ne sont pas dans le magasin approprié, vous verrez l’état récapitulatif, comme illustré dans l’image suivante. Vous n’avez pas l’option d’assigner le certificat. Pour terminer le processus d’affectation de certificat, vous devez importer le certificat racine de l’autorité de certification ainsi que tous les certificats intermédiaires de l’autorité de certification, puis assigner le certificat en cliquant sur **Assigner** dans la page principale de l’Assistant Certificat.
  


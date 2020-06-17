---
title: Configuration des enregistrements DNS pour le déploiement d’un pool pilote
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote. Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754054"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configuration des enregistrements DNS pour le déploiement d’un pool pilote

Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote. Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Pour configurer des enregistrement d’hôte DNS (A)

1. Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.
    
2. Dans l’arborescence de la console de votre domaine, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine dans lequel Skype entreprise Server 2019 sera installé.
    
3. Cliquez sur **Nouvel hôte (A ou AAAA)**.
    
4. Cliquez sur **nom**, tapez le nom d’hôte du pool Skype entreprise Server 2019 (le nom de domaine est supposé à partir de la zone dans laquelle l’enregistrement est défini et il n’est pas nécessaire de l’entrer comme partie de l’enregistrement A).
    
5. Cliquez sur **adresse IP**, puis tapez l’adresse IP du pool frontal.
    
6. Cliquez sur **Ajouter un hôte**, puis sur **OK**. 
    
7. Lorsque vous avez terminé, cliquez sur **Terminé**.
    


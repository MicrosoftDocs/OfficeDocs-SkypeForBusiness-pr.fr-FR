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
ms.openlocfilehash: 270b0bda7da679cb0c75e9a99e10a898dcee6ac70413ce276abfe19ba1eb2231
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337832"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>Configuration des enregistrements DNS pour le déploiement d’un pool pilote

Avant de déployer le pool pilote, vous devez mettre à jour les entrées d’hôte DNS A pour le pool pilote. Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
  
### <a name="to-configure-dns-host-a-records"></a>Pour configurer des enregistrement d’hôte DNS (A)

1. Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.
    
2. Dans l’arborescence de la console de votre domaine, développez **Zones** de recherche avant, puis cliquez avec le bouton droit sur le domaine dans lequel Skype Entreprise Server 2019 sera installé.
    
3. Cliquez sur **Nouvel hôte (A ou AAAA)**.
    
4. Cliquez sur Nom **,** tapez le nom d’hôte pour le pool Skype Entreprise Server 2019 (le nom de domaine est supposé dans la zone où l’enregistrement est défini et n’a pas besoin d’être entré dans le cadre de l’enregistrement A).
    
5. Cliquez **sur Adresse IP,** puis tapez l’adresse IP du pool frontal.
    
6. Cliquez sur **Ajouter un hôte**, puis sur **OK**. 
    
7. Lorsque vous avez terminé, cliquez sur **Terminé**.
    


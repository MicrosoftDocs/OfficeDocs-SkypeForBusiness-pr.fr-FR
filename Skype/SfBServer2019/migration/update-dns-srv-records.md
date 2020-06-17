---
title: Mettre à jour les enregistrements SRV DNS
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
description: Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753266"
---
# <a name="update-dns-srv-records"></a>Mettre à jour les enregistrements SRV DNS

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
  
Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Skype entreprise Server 2019. Une fois que tous les utilisateurs ont été déplacés vers Skype entreprise Server 2019, mais avant que le pool hérité ou le directeur ne soit désactivé, vous devez mettre à jour les enregistrements SRV DNS dans votre DNS interne pour chaque domaine SIP. Cela présuppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Pour configurer un enregistrement DNS SRV

1. Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.
    
2. Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, développez le domaine SIP dans lequel Skype for Business Server 2019 est installé, puis accédez au paramètre **_tcp** . 
    
3. Dans le volet droit, cliquez avec le bouton droit sur **_sipinternaltls** et sélectionnez **Propriétés**.
    
4. Dans **hôte offrant ce service**, mettez à jour le nom de domaine complet de l’hôte de sorte qu’il pointe vers le pool Skype entreprise Server 2019.
    
5. Cliquez sur **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu

1. Ouvrez une session sur un ordinateur client du domaine.
    
2. Cliquez sur **Démarrer**, puis sur **Exécuter**.
    
3. Dans la zone **ouvrir** , tapez cmd, puis cliquez sur **OK**.
    
4. À l’invite de commandes, tapez nslookup _\<FQDN of the Front End pool\>_ ou _\<FQDN of the Standard Edition server\>_ , puis appuyez sur entrée.
    
5. Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.
    


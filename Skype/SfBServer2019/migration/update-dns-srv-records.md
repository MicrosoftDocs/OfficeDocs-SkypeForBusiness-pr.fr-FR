---
title: Mettre à jour les enregistrements SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812772"
---
# <a name="update-dns-srv-records"></a>Mettre à jour les enregistrements SRV DNS

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.
  
Cette rubrique explique comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Skype entreprise Server 2019. Après le déplacement de tous les utilisateurs vers Skype entreprise Server 2019, mais avant la désactivation du pool ou du réalisateur hérités, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP. Cette procédure part du principe que votre DNS interne comporte des zones pour vos domaines d’utilisateur SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Pour configurer un enregistrement SRV DNS

1. Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.
    
2. Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, développez le domaine SIP dans lequel Skype entreprise Server 2019 est installé, puis accédez au paramètre **_tcp** . 
    
3. Dans le volet droit, cliquez avec le bouton droit sur **_sipinternaltls** et sélectionnez **Propriétés**.
    
4. Dans la liste des **hôtes proposant ce service**, mettez à jour le nom de domaine complet (FQDN) de l’hôte pour qu’il pointe sur le pool Skype entreprise Server 2019.
    
5. Cliquez sur **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Pour vérifier que le nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition peut être résolu

1. Connectez-vous à un ordinateur client dans le domaine.
    
2. Cliquez sur **Démarrer **, puis sur **Exécuter **.
    
3. Dans la zone **ouvrir** , tapez cmd, puis cliquez sur **OK**.
    
4. À l’invite de commandes, tapez nslookup _ \<FQDN du pool\> frontal_ ou _ \<du FQDN du serveur\>Standard Edition_, puis appuyez sur entrée.
    
5. Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).
    


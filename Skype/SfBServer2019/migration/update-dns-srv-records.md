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
ms.openlocfilehash: 0c3454bd4fbf8ecdc28730da378357e9d50efec3c12ba5b3926abb61010979ab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327050"
---
# <a name="update-dns-srv-records"></a>Mettre à jour les enregistrements SRV DNS

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.
  
Cette rubrique décrit comment mettre à jour les enregistrements DNS (Domain Name System) après la migration vers Skype Entreprise Server 2019. Une fois que tous les utilisateurs ont été déplacés vers Skype Entreprise Server 2019, mais avant la désaffectation du pool ou du directeur hérité, vous devez mettre à jour les enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP. Cela présuppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.
  
## <a name="to-configure-a-dns-srv-record"></a>Pour configurer un enregistrement DNS SRV

1. Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.
    
2. Dans l’arborescence de la console pour votre domaine SIP, développez zones de recherche **avant,** développez le domaine SIP dans lequel Skype Entreprise Server 2019 est installé et accédez au **paramètre _tcp..** 
    
3. Dans le volet droit, cliquez avec le bouton **droit sur _sipinternaltls** puis sélectionnez **Propriétés.**
    
4. Dans **host offering this service**, update the host FQDN to point to the Skype Entreprise Server 2019 pool.
    
5. Cliquez sur **OK**.
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu

1. Ouvrez une session sur un ordinateur client du domaine.
    
2. Cliquez sur **Démarrer**, puis sur **Exécuter**.
    
3. Dans la **zone Ouvrir,** tapez cmd, puis cliquez sur **OK.**
    
4. À l’invite de commandes, tapez nslookup _\<FQDN of the Front End pool\>_ ou  _\<FQDN of the Standard Edition server\>_ , puis appuyez sur Entrée.
    
5. Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.
    


---
title: Déploiement de l’outil SEFAUtil dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Déploiement de l’outil SEFAUtil dans Skype pour Business Server.
ms.openlocfilehash: 4def73d0bca655569275f61d9ebfeafb4ab7e3d4
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>Déploiement de l’outil SEFAUtil dans Skype Entreprise 2015
 
Déploiement de l’outil SEFAUtil dans Skype pour Business Server.
  
Pour déployer et gérer la collecte d’appel de groupe, vous devez utiliser le Skype pour la version de l’outil SEFAUtil Business Server. 
  
> [!IMPORTANT]
> Exécution de Microsoft Unified Communications Managed API (UCMA) 5 doit être installée sur tout ordinateur où vous prévoyez d’exécuter l’outil SEFAUtil. Télécharger ici : [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Vous pouvez également télécharger le SDK UCMA 5, qui inclut le runtime ici : [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal dans votre déploiement. Pour exécuter l’outil SEFAUtil, vous devez exécuter les étapes 1, 2 et 3 depuis le Skype pour l’Assistant de déploiement d’entreprise sur l’ordinateur d’applications approuvées. SEFAUtil requiert le magasin de configurations local à présent, ainsi que d’un certificat.
  
> [!NOTE]
> Pour plus d’informations sur l’exécution de SEFAUtil, consultez l’article de blog Technet, «[comment obtenir SEFAutil en cours d’exécution ?](https://go.microsoft.com/fwlink/?LinkId=278940)». 
  
### <a name="to-deploy-sefautil"></a>Pour déployer SEFAUtil

1. Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées. Si nécessaire, définir un pool d’applications approuvées pour le pool frontal où vous prévoyez d’exécuter SEFAUtil. Dans la ligne de commande, exécutez la commande suivante :
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. Définissez l’outil SEFAUtil en tant qu’application approuvée. Sur la ligne de commande, exécutez :
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Vous pouvez utiliser un autre port si nécessaire. 
  
5. Activez la topologie avec vos modifications. Sur la ligne de commande, exécutez :
    
  ```
  Enable-CsTopology
  ```

6. Si vous n’avez pas déjà, téléchargez le Skype pour la version de l’outil SEFAUtil Business Server à partir de [cet emplacement](https://www.microsoft.com/en-us/download/details.aspx?id=52631)et les installer sur le pool d’applications approuvées créé à l’étape 3.
    
7. Vérifiez que l’outil SEFAUtil s’exécute correctement ainsi : 
    
    a. Exécutez l’outil à partir de l’invite de commande Windows avec des droits d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur de votre déploiement.
    
    b. Affichez les paramètres de transfert d’appel d’un utilisateur. Sur la ligne de commande, exécutez :
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

Les paramètres de transfert d’appel de l’utilisateur s’afficheront.
    


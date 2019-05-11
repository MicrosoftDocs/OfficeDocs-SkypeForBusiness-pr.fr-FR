---
title: Déploiement de l’outil SEFAUtil dans Skype pour les entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Déploiement de l’outil SEFAUtil dans Skype pour Business Server.
ms.openlocfilehash: 0122c2f118bc04cbdc8631e50c688982df16d99a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892635"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Déploiement de l’outil SEFAUtil dans Skype pour les entreprises
 
Déploiement de l’outil SEFAUtil dans Skype pour Business Server.
  
Pour déployer et gérer la collecte d’appel de groupe, vous devez utiliser le Skype pour la version de l’outil SEFAUtil Business Server. 
  
> [!IMPORTANT]
> Exécution de Microsoft Unified Communications Managed API (UCMA) 5 doit être installée sur tout ordinateur où vous prévoyez d’exécuter l’outil SEFAUtil. Télécharger ici : [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Vous pouvez également télécharger le SDK UCMA 5, qui inclut le runtime ici : [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal dans votre déploiement. Pour exécuter l’outil SEFAUtil, vous devez exécuter les étapes 1, 2 et 3 depuis le Skype pour l’Assistant de déploiement d’entreprise sur l’ordinateur d’applications approuvées. SEFAUtil requiert le magasin de configurations local à présent, ainsi que d’un certificat.
  
> [!NOTE]
> Pour plus d’informations sur l’exécution de SEFAUtil, voir l’article de blog, «[comment obtenir SEFAutil en cours d’exécution ?](https://go.microsoft.com/fwlink/?LinkId=278940)». 
  
### <a name="to-deploy-sefautil"></a>Pour déployer SEFAUtil

1. Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées. Si nécessaire, définir un pool d’applications approuvées pour le pool frontal où vous prévoyez d’exécuter SEFAUtil. Sur la ligne de commande, exécutez :
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Nom de domaine complet de pool : Nom de domaine complet du serveur ou du pool qui hébergera l’application SEFAUtil (généralement un Skype pour le serveur frontal métiers ou du pool).
    > Registrar nom de domaine complet de pool : Nom de domaine complet de le Skype pour Business frontal ou pool associé à ce pool d’applications.
    > Site de pool : L’ID de Site du site sur lequel ce pool est hébergé.

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
    


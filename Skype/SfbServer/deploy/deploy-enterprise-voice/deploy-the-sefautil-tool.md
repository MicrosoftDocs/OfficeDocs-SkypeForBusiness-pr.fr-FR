---
title: Déploiement de l’outil SEFAUtil dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Déploiement de l’outil SEFAUtil dans Skype entreprise Server.
ms.openlocfilehash: ab0d41990e0c4bf9d4d2abb635ce447180899de8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767497"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Déploiement de l’outil SEFAUtil dans Skype entreprise
 
Déploiement de l’outil SEFAUtil dans Skype entreprise Server.
  
Pour déployer et gérer la cueillette des appels de groupe, vous devez utiliser la version de Skype entreprise Server de l’outil SEFAUtil. 
  
> [!IMPORTANT]
> L’utilisation de l’API Microsoft Unified Communications Managed API (UCMA) 5 doit être installée sur tout ordinateur sur lequel vous envisagez d’exécuter l’outil SEFAUtil. Téléchargez-le ici : [API d’API managée de communications unifiées 5,0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344). Vous pouvez également télécharger le kit de développement logiciel (SDK) UCMA 5, qui inclut le runtime, ici : [UCMA 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
Vous pouvez exécuter l’outil SEFAUtil dans n’importe quel pool frontal de votre déploiement. Pour exécuter l’outil SEFAUtil, vous devez exécuter les étapes 1, 2 et 3 de l’Assistant Déploiement de Skype entreprise sur l’ordinateur de l’application de confiance. SEFAUtil nécessite la présence du magasin de configuration local ainsi qu’un certificat.
  
> [!NOTE]
> Pour plus d’informations sur l’exécution de SEFAUtil, voir l’article de blog intitulé « Comment puis-[je exécuter SEFAUtil ?](https://go.microsoft.com/fwlink/?LinkId=278940)». 
  
### <a name="to-deploy-sefautil"></a>Pour déployer SEFAUtil

1. Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans **autorisations de configuration de délégué**.
    
2. Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. L’outil SEFAUtil ne peut être exécuté que sur un ordinateur qui fait partie d’un pool d’applications approuvées. Le cas échéant, définissez un pool d’applications approuvé pour le pool frontal sur lequel vous envisagez d’exécuter SEFAUtil. Sur la ligne de commande, exécutez :
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > Nom de domaine complet (FQDN) du pool : nom de domaine complet (FQDN) du serveur ou du pool hébergeant l’application SEFAUtil (généralement un serveur frontal ou un pool Skype entreprise).
    > Nom de domaine complet (FQDN) de pool : nom de domaine complet (FQDN) du serveur frontal ou du pool Skype entreprise associé à ce pool d’applications.
    > Site du pool : ID de site du site sur lequel ce pool est hébergé.

4. Définissez l’outil SEFAUtil en tant qu’application approuvée. Sur la ligne de commande, exécutez :
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Vous pouvez utiliser un autre port si nécessaire. 
  
5. Activez la topologie avec vos modifications. Sur la ligne de commande, exécutez :
    
   ```powershell
   Enable-CsTopology
   ```

6. Si ce n’est déjà fait, téléchargez la version Skype entreprise Server de l’outil SEFAUtil à partir de [cet emplacement](https://www.microsoft.com/en-us/download/details.aspx?id=52631)et installez-la sur le pool d’applications approuvé que vous avez créé à l’étape 3.
    
7. Vérifiez que l’outil SEFAUtil s’exécute correctement ainsi : 
    
    a. Exécutez l’outil à partir de l’invite de commande Windows avec des droits d’administrateur pour afficher les paramètres de transfert d’appel d’un utilisateur de votre déploiement.
    
    b. Affichez les paramètres de transfert d’appel d’un utilisateur. Sur la ligne de commande, exécutez :
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Les paramètres de transfert d’appel de l’utilisateur s’afficheront.
    


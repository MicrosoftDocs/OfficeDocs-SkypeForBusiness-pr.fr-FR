---
title: Gérer les paramètres de configuration des services Web dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Résumé : gérez les paramètres de configuration des services Web dans Skype entreprise Server.'
ms.openlocfilehash: 2ab23e499cff7678ddb50c57cdc6f396a3c4203c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818676"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration des services Web dans Skype entreprise Server
 
**Résumé :** Gérer les paramètres de configuration des services Web dans Skype entreprise Server.
  
Vous pouvez utiliser la page de **service Web** pour configurer les méthodes d’authentification pour l’accès à Skype entreprise Server et aux services Web.
  
Pour créer une stratégie de service web, procédez comme suit.
  
### <a name="to-create-new-web-service-configuration-settings"></a>Pour créer des paramètres de configuration d’un service web

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.
    
4. Dans la page **Service web**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
   - Pour configurer le service web pour un site, cliquez sur **Configuration du site**. Dans **Sélectionner un site**, cliquez sur le site auquel le service web s’appliquera, puis cliquez sur **OK**.
    
   - Pour configurer le service web pour un pool, cliquez sur **Configuration du pool**. Dans **Sélectionner un service**, cliquez sur le service auquel la stratégie de service web s’appliquera, puis cliquez sur **OK**. 
    
5. Dans **Nouveau paramètre de service web**, dans **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucun**.
    
6. Sélectionnez une ou plusieurs des options ci-dessous en fonction des capacités des clients et de la prise en charge dans votre environnement :
    
   - **Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
   - **Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.
    
7. Cliquez sur **Valider**.
    
## <a name="modify-existing-web-service-configuration-settings"></a>Modification des paramètres de configuration d’un service web existant

Vous pouvez utiliser la page de **service Web** pour configurer les méthodes d’authentification pour l’accès à Skype entreprise Server et aux services Web.
  
Pour modifier une stratégie de service web existante, procédez comme suit.
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>Pour modifier des paramètres de configuration d’un service web existant

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.
    
4. Dans la page **Service web**, sélectionnez une configuration, cliquez sur le menu **Edition**, puis sur **Afficher les détails**.
    
5. Dans **Modifier le paramètre de service web**, sous **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucune**.
    
6. Sélectionnez une ou plusieurs des options ci-dessous en fonction des capacités des clients et de la prise en charge dans votre environnement :
    
   - **Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
   - **Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.
    
7. Cliquez sur **Valider**.
    
## <a name="delete-existing-web-service-configuration-settings"></a>Suppression des paramètres de configuration d’un service web existant

Pour supprimer les paramètres de configuration des services web, procédez comme suit.
  
### <a name="to-delete-web-service-configuration-settings"></a>Pour supprimer des paramètres de configuration d’un service web existant

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.
    
4. Dans le champ de recherche de la page **Service web**, tapez l’intégralité ou une partie du nom de la stratégie à supprimer.
    
5. Dans la liste des stratégies, cliquez sur la stratégie à supprimer, sur **Modifier**, puis sur **Supprimer**.
    
6. Cliquez sur **OK**.
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Supprimer des paramètres de configuration de service Web à l’aide des applets de cmdlet Windows PowerShell

Vous pouvez supprimer des paramètres de configuration de service Web à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsWebServiceConfiguration** . Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Pour supprimer une collection de paramètres de configuration des services web

- La commande ci-dessous supprime les paramètres de sécurité des services web appliqués au site de Redmond :
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration des services web appliqués à l’étendue du site

La commande ci-dessous supprime tous les paramètres de sécurité des services web appliqués à l’étendue des services :
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Pour supprimer tous les paramètres de configuration des services web qui autorisent l’authentification des certificats

La commande ci-dessous supprime tous les paramètres de sécurité des services web qui autorisent l’authentification des certificats :
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

Pour plus d’informations, consultez la rubrique [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).
  


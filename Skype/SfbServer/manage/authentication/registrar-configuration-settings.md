---
title: Gérer les paramètres de configuration du serveur d’inscriptions dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Résumé : Gérez les paramètres de configuration du serveur d’inscriptions pour Skype Entreprise Server.'
ms.openlocfilehash: 8413d7d1604a598b8c46cebe753d408d9300d823
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015008"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration du serveur d’inscriptions dans Skype Entreprise Server
 
**Résumé :** Gérer les paramètres de configuration du serveur d’inscriptions pour Skype Entreprise Server.
  
Vous pouvez utiliser le serveur d’inscriptions pour configurer les méthodes d’authentification du serveur proxy. Le protocole d’authentification que vous spécifiez détermine le type de défis que les serveurs du pool doivent relever aux clients. Les protocoles disponibles sont :
  
- **Kerberos** Il s’agit du schéma d’authentification par mot de passe le plus fort disponible pour les clients, mais il est généralement disponible uniquement pour les clients d’entreprise, car il nécessite une connexion client à un centre de distribution de clés (contrôleur de domaine Kerberos). Ce paramètre est approprié si le serveur authentifier uniquement les clients d’entreprise.
    
- **NTLM** Il s’agit de l’authentification par mot de passe disponible pour les clients qui utilisent un schéma de hachage challenge-response sur le mot de passe. Il s’agit de la seule forme d’authentification disponible pour les clients sans connectivité à un centre de distribution de clés (contrôleur de domaine Kerberos), comme les utilisateurs distants. Si un serveur authentifier uniquement les utilisateurs distants, vous devez choisir NTLM.
    
- **Authentification de certificat** Il s’agit de la nouvelle méthode d’authentification lorsque le serveur doit obtenir des certificats auprès de clients Lync Phone Edition, de téléphones de partie commune, de Skype Entreprise et de l’application Lync du Windows Store. Sur les clients Lync Phone Edition, une fois qu’un utilisateur s’est correctement authentifié en fournissant un code confidentiel, Skype Entreprise Server met ensuite en service l’URI SIP sur le téléphone et met en service un certificat signé Skype Entreprise Server ou un certificat d’utilisateur qui identifie Joe (Ex: SN=joe@contoso.com ) sur le téléphone. Ce certificat est utilisé pour l’authentification auprès du serveur d’inscriptions et des services Web.
    
> [!NOTE]
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé. 
  
Si vous utilisez les clients d’application du Windows Store Lync, vous devez activer l’authentification par certificat.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Pour créer de nouveaux paramètres de configuration du bureau d’enregistrement d’inscriptions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.
    
4. Dans la page **Du bureau d’enregistrement,** cliquez sur **Nouveau**
    
5. Dans **Sélectionner un service,** cliquez sur le service auquel le bureau d’inscriptions doit être appliqué, puis cliquez sur **OK.**
    
6. Dans Nouveau paramètre du bureau **d’enregistrement,** sélectionnez une ou plusieurs des fonctionnalités suivantes en fonction des fonctionnalités des clients et de la prise en charge dans votre environnement :
    
   - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
   - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
7. Cliquez sur **Valider**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modifier les paramètres de configuration du bureau d’enregistrement d’inscriptions existant

Vous pouvez utiliser le serveur d’inscriptions pour configurer les protocoles d’authentification du serveur proxy. 
  
> [!NOTE]
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé. 
  
Procédez comme suit pour modifier un serveur d’inscription existant. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Pour modifier les paramètres de configuration du bureau d’enregistrement existant

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.
    
4. Dans la page **Serveur d’inscriptions**, cliquez sur un service, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier le paramètre du serveur d’inscriptions**, sélectionnez un ou plusieurs des éléments suivants selon les fonctionnalités des clients et la prise en charge de votre environnement :
    
   - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
   - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
6. Cliquez sur **Valider**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Pour supprimer les paramètres de configuration du bureau d’enregistrement d’inscriptions

1. À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.
    
4. Dans la page **Serveur d’inscriptions**, dans le champ de recherche, tapez entièrement ou partiellement le nom du serveur d’inscriptions que vous voulez supprimer.
    
5. Dans la liste, cliquez sur le serveur d’inscriptions souhaité, cliquez sur **Modifier**, puis sur **Supprimer**.
    
6. Cliquez sur **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration du bureau d’enregistrement d’inscriptions Windows PowerShell cmdlets

Vous pouvez supprimer les paramètres de configuration du bureau d’enregistrement d’inscriptions à l Windows PowerShell applet **remove-CsProxyConfiguration.** Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/).
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Pour supprimer un ensemble spécifique de paramètres de sécurité du serveur d’inscriptions avancé

- La commande suivante supprime les paramètres de sécurité du serveur d’inscriptions avancé appliqués au serveur Edge atl-edge-011.litwareinc.com :
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués l’étendue Site

- La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués au service de serveur d’inscriptions avancé :
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’authentification NTLM

- La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’utilisation de NTLM pour l’authentification client :
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Pour plus d’informations, [voir Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).

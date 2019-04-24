---
title: Gérer les paramètres de configuration du serveur d’inscriptions dans Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Résumé : Gérer les paramètres de configuration de serveur d’inscriptions de Skype pour Business Server.'
ms.openlocfilehash: a1dda801049313cc2fc4dead94b524c300885924
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217312"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>Gérer les paramètres de configuration du serveur d’inscriptions dans Skype pour Business Server
 
**Résumé :** Gérer les paramètres de configuration de serveur d’inscriptions de Skype pour Business Server.
  
Vous pouvez utiliser le serveur d’inscriptions avancé pour configurer les méthodes d’authentification du serveur proxy. Le protocole d’authentification que vous spécifiez détermine le type de difficultés que les serveurs du pool posent aux clients. Les protocoles disponibles sont les suivants :
  
- **Kerberos** C’est le modèle d’authentification par mot de passe le plus puissant aux clients, mais il est généralement disponible uniquement pour les clients d’entreprise, car il exige une connexion client à un centre de Distribution de clés (contrôleur de domaine Kerberos). Ce paramètre est adapté si le serveur ne doit authentifier que des clients entreprise.
    
- **NTLM** Il s’agit de l’authentification par mot de passe pour les clients qui utilisent un schéma de hachage stimulation / réponse au mot de passe. C’est la seule forme d’authentification proposée aux clients ne disposant pas d’une connectivité à un centre de distribution des clés (contrôleur de domaine Kerberos), comme les utilisateurs distants. Si un serveur n’authentifie que des utilisateurs distants, vous devez choisir NTLM.
    
- **Authentification par certificat** Il s’agit de la méthode d’authentification lorsque le serveur doit obtenir des certificats à partir de clients Lync Phone Edition, les téléphones de partie commune, Skype pour les entreprises et l’application Lync Windows Store. Sur les clients Lync Phone Edition, après un utilisateur se connecte et est authentifié avec succès en fournissant un code confidentiel (PIN), Skype pour Business Server, puis met en service l’URI SIP sur le téléphone et met en service un Skype pour Business Server connecté certificat ou un certificat utilisateur qui identifie Joe (Ex : SN=joe@contoso.com) sur le téléphone. This certificate is used for authenticating with the Registrar and Web Services.
    
> [!NOTE]
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également sur le serveur, Kerberos est utilisé. 
  
Si vous utilisez les clients d’application Lync Windows Store, vous devez activer l’authentification par certificat.
  
### <a name="to-create-new-registrar-configuration-settings"></a>Pour créer des paramètres de configuration du serveur d’inscriptions avancé

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.
    
4. Dans la page **Serveur d’inscriptions avancé**, cliquez sur **Nouveau**.
    
5. Dans **Sélectionner un service**, cliquez sur le service auquel le serveur d’inscriptions avancé s’appliquera, puis cliquez sur **OK**.
    
6. Dans **Nouveau paramètre de serveur d’inscriptions avancé**, sélectionnez un ou plusieurs des éléments ci-dessous selon les fonctionnalités des clients et la prise en charge de votre environnement :
    
   - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
   - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
7. Cliquez sur **Valider**.
    
## <a name="modify-existing-registrar-configuration-settings"></a>Modification des paramètres de configuration d’un serveur d’inscriptions avancé existant

Vous pouvez utiliser le serveur d’inscriptions avancé pour configurer les protocoles d’authentification du serveur proxy. 
  
> [!NOTE]
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également sur le serveur, Kerberos est utilisé. 
  
Pour modifier un serveur d’inscriptions avancé, procédez comme suit. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>Pour modifier des paramètres de configuration d’un serveur d’inscriptions avancé existant

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.
    
4. Dans la page **Serveur d’inscriptions avancé**, sélectionnez un service, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier le paramètre du serveur d’inscriptions avancé**, sélectionnez un ou plusieurs des éléments ci-dessous selon les fonctionnalités des clients et la prise en charge de votre environnement :
    
   - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
   - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
   - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.
    
6. Cliquez sur **Valider**.
    
### <a name="to-delete-registrar-configuration-settings"></a>Pour supprimer des paramètres de configuration du serveur d’inscriptions avancé

1. À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.
    
4. Dans la page **Serveur d’inscriptions avancé**, dans le champ de recherche, tapez entièrement ou partiellement le nom du serveur d’inscriptions avancé à supprimer.
    
5. Dans la liste, sélectionnez le serveur d’inscriptions avancé souhaité, cliquez sur **Modifier**, puis sur **Supprimer**.
    
6. Cliquez sur **OK**.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de Configuration du serveur d’inscriptions à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration du serveur d’inscriptions à l’aide de Windows PowerShell et l’applet de commande **Remove-CsProxyConfiguration** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Pour supprimer un ensemble spécifique de paramètres de sécurité du serveur d’inscriptions avancé

- La commande ci-dessous supprime les paramètres de sécurité du serveur d’inscriptions avancé appliqués au serveur Edge atl-edge-011.litwareinc.com :
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués à l’étendue Site

- La commande ci-dessous supprime tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués au service de serveur d’inscriptions avancé :
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’authentification NTLM

- La commande ci-dessous supprime tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’utilisation de NTLM pour l’authentification client :
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

Pour plus d’informations, voir [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).
  


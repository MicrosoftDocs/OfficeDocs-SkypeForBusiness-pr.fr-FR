---
title: Déployer des clients web téléchargeables dans Skype Entreprise Server
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Résumé : Déployez l’application Application Web Skype Entreprise et Skype Réunions utilisée avec Skype Entreprise.'
ms.openlocfilehash: c262ab4e9180ae9e02bc899793437a86ffe12ead
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761592"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Déployer des clients web téléchargeables dans Skype Entreprise Server

**Résumé :** Déployez Skype Entreprise 2015 Web App et Skype Meetings App utilisés avec Skype Entreprise Server.

Application Web Skype Entreprise est un client web Internet Information Services (IIS) installé sur le serveur exécutant Skype Entreprise Server et déployé par défaut à la demande pour répondre aux utilisateurs qui n’ont pas encore le client Skype Entreprise. Ces utilisateurs de réunion se connectent le plus souvent depuis l’extérieur de votre réseau. Chaque fois qu’un utilisateur clique sur une URL de réunion, mais que le client Skype Entreprise n’est pas installé, l’utilisateur peut participer à la réunion à l’aide de la dernière version de Application Web Skype Entreprise, de l’application Skype Meetings ou de Skype Entreprise pour Mac.

Les fonctionnalités vocales, vidéo et de partage dans Application Web Skype Entreprise nécessitent un contrôle Microsoft ActiveX utilisé comme plug-in par le navigateur de l’utilisateur. Vous pouvez installer le contrôle ActiveX à l’avance ou autoriser les utilisateurs à l’installer à l’invite, ce qui se produit la première fois qu’ils utilisent Application Web Skype Entreprise ou la première fois qu’ils accèdent à une fonctionnalité nécessitant le contrôle ActiveX.

> [!NOTE]
> Dans Skype Entreprise Server de serveur Edge, un proxy inverse HTTPS dans le réseau de périmètre est requis pour l Application Web Skype Entreprise client. Vous devez également publier des URL simples. Pour plus d’informations, voir [Configuration des serveurs proxy](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) inverses et des exigences [DNS](../../plan-your-deployment/network-requirements/simple-urls.md)pour les URL simples dans Skype Entreprise Server .

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Activer l’authentification multifacteur pour Application Web Skype Entreprise
<a name="MFA"> </a>

Application Web Skype Entreprise, Skype Meetings App et Skype Entreprise pour Mac l’authentification multifacteur. Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des code pin pin, pour authentifier les utilisateurs qui rejoignent des réseaux externes lorsqu’ils se connectent à Skype Entreprise réunions. Vous pouvez activer l’authentification multifacteur en déployant le serveur de fédération AD FS (Active Directory Federation Service) et en activant l’authentification passive dans Skype Entreprise Server. Une fois les services AD FS configurés, les utilisateurs externes qui tentent de participer à des réunions Skype Entreprise se présentent avec une page web d’authentification multifacteur AD FS qui contient le nom d’utilisateur et le mot de passe, ainsi que les méthodes d’authentification supplémentaires que vous avez configurées.

> [!IMPORTANT]
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :

- L’authentification ADFS multifacteur fonctionne si le participant à la réunion et l’organisateur font tous deux partie de la même organisation ou d’une organisation fédérée AD FS. L’authentification ADFS multifacteur ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web Lync Server ne la prend actuellement pas en charge.

- Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge afin que toutes les demandes des clients Application Web Skype Entreprise ou d’application Réunions soient gérées par le même serveur frontal.

- Lorsque vous établissez une relation d’confiance entre les serveurs Skype Entreprise Server et AD FS, attribuez une durée de vie de jeton suffisamment longue pour englober la durée maximale de vos réunions Skype Entreprise. Une durée de vie de jeton de 240 minutes est généralement suffisante.

- Cette configuration ne s’applique pas aux clients mobiles Lync.

### <a name="configure-multi-factor-authentication"></a>Configurer l’authentification multifacteur

1. Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, voir le Guide de déploiement des services de fédération [Active Directory 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. Créez des certificats pour AD FS. Pour plus d’informations, voir la section « [Certificats](/previous-versions/azure/azure-services/jj205462(v=azure.100)) de serveur de fédération » de la rubrique Plan for and deploy AD FS for use with single sign-on topic.

3. À partir Windows PowerShell’interface de ligne de commande, exécutez la commande suivante :

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Établissez un partenariat en exécutant la commande suivante :

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Définissez les règles de partie de confiance suivantes :

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Désactiver BranchCache
<a name="MFA"> </a>

La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec Application Web Skype Entreprise composants web. Pour éviter les problèmes pour Application Web Skype Entreprise utilisateurs, assurez-vous que BranchCache n’est pas activé.

Pour plus d’informations sur la désactivation de BranchCache, voir le [Guide de déploiement de BranchCache.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>Vérification du Application Web Skype Entreprise déploiement
<a name="MFA"> </a>

Vous pouvez utiliser l’applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l’aide de l’API UCWA (Unified Communications Web API). Pour plus d’informations sur cette cmdlet, voir [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) dans la documentation Skype Entreprise Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Résolution des problèmes d’installation du plug-in sur Windows Server 2008 R2
<a name="MFA"> </a>

Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité d’Internet Explorer ou le paramètre de clé de Registre DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modifier le paramètre de sécurité dans Internet Explorer

1. Ouvrez Internet Explorer.

2. Cliquez sur **Outils**, sur **Options Internet**, puis sur **Avancé**.

3. Faites défiler la page vers le bas jusqu’à la section **Sécurité**.

4. Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK**.

    > [!NOTE]
    > S’il est sélectionné, ce paramètre provoque également une erreur lors de la tentative de téléchargement d’une pièce jointe à partir Application Web Skype Entreprise.

5. Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.

### <a name="modify-the-disablemsi-registry-setting"></a>Modifier le paramètre de Registre DisableMSI

1. Cliquez sur **Démarrer**, puis sur **Exécuter**.

2. Pour accéder à l’Éditeur du Registre, tapez **regedit**.

3. Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.

5. Rejoignez la réunion.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Activer Skype l’application Réunions pour remplacer Application Web Skype Entreprise (facultatif, Skype Entreprise Server 2015 uniquement)
<a name="SMA_Enable"> </a>

Cette procédure est facultative et s’applique Skype Entreprise Server cu5 2015 et ultérieures. Si vous ne l’utilisez pas, les utilisateurs externes continueront à participer aux réunions à l’aide Application Web Skype Entreprise.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Activer l’application de réunion Skype réunions simplifiée

1. Lorsque vous activez l’accès au réseau de distribution de contenu (CDN), les utilisateurs ont la possibilité de se connecter à CDN en ligne et d’obtenir l’application Skype Meetings (sur Windows) et Skype Entreprise pour Mac (sur Mac), et utilisent la réunion simplifiée. expérience.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Autoriser l’envoi de la télémétrie de journalisation côté client à partir de la page web de connexion à une réunion ou de l’application Skype Meetings aux serveurs Microsoft (la commande est false par défaut).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Les informations envoyées à Microsoft sont strictement conformes aux [pratiques Skype Entreprise de collecte de données.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. Définissez le délai avant de revenir à l’expérience Application Web Skype Entreprise hébergée localement si CDN n’est pas disponible. La valeur par défaut est 6 secondes. Si cette valeur est définie sur 0, il n’y aura pas de délai d’accès.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> With MeetingUxUseCdn in Skype Entreprise Server 2015 Cumulative Update 5, the default value is set to False. Cela provoque un problème dans lequel le client Skype Entreprise pour Mac ne peut pas participer aux réunions des partenaires non fédérés en tant qu’invité, même si l’administrateur Skype Entreprise Skype Entreprise définie MeetingUxUseCdn sur True. Pour que cela fonctionne, Skype Entreprise Server 2015 doit avoir la mise à jour cumulative 7, 6.0.9319.534 ou ultérieure. Voir Activer Skype l’application Réunions pour remplacer Application Web Skype Entreprise [dans Skype Entreprise Server 2015.](https://support.microsoft.com/kb/4132312)


## <a name="see-also"></a>Voir aussi
<a name="SMA_Enable"> </a>

[Planifier les clients Meetings (application Web et application réunions)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurer la page de réunion dans Skype Entreprise Server](../../manage/conferencing/meeting-join-page.md)

[Déclaration de confidentialité de Microsoft](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[Termes et documentation sur les licences](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
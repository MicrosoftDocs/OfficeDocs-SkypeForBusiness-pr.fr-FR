---
title: Déployer des clients Web téléchargeables Skype pour Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Résumé : Déployez le Skype pour l’application Web de gestion et application de réunions Skype utilisé avec Skype pour les entreprises.'
ms.openlocfilehash: 5d98c0089f7ba45c4efd5f36a3f5b61b759f6238
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895240"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Déployer des clients Web téléchargeables Skype pour Business Server

**Résumé :** Déployer le Skype pour Business 2015 Web App et application de réunions Skype utilisé avec Skype pour Business Server.

Skype pour Business Web App est un client web Internet Information Services (IIS) qui est installé sur le serveur exécutant Skype pour Business Server et par défaut, il est déployé sur la demande aux utilisateurs de réunion qui n’ont pas encore le Skype pour client d’entreprise. Ces utilisateurs de réunion sont le plus souvent que ne pas connexion depuis l’extérieur de votre réseau. Chaque fois qu’un utilisateur clique sur une URL de réunion, mais n’a pas la Skype pour Business client est installé, l’utilisateur voit s’afficher avec la possibilité de participer à la réunion à l’aide de la dernière version de Skype pour Business Web App, application de réunions Skype ou Skype pour les entreprises pour Mac.

Les fonctionnalités de la voix, vidéo et partage dans Skype pour l’application Web de gestion nécessitent un contrôle Microsoft ActiveX qui est utilisé comme un plug-in par le navigateur de l’utilisateur. Vous pouvez installer le contrôle ActiveX à l’avance ou autoriser les utilisateurs à installer lorsque vous y êtes invité, ce qui se produit la première fois qu’ils utilisent Skype pour Business Web App ou la première fois qu’ils accèdent à une fonctionnalité qui requiert le contrôle ActiveX.

> [!NOTE]
> Dans Skype pour les déploiements de serveur de périphérie Business Server, un proxy inverse HTTPS dans le réseau de périmètre est requis pour Skype pour l’accès client Business Web App. Vous devez également publier des URL simples. Pour plus d’informations, voir [Configuration des serveurs Proxy inverse](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) et les [enregistrements DNS requis pour les URL simples dans Skype pour Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Activer l’authentification multifacteur pour Skype pour Business Web App
<a name="MFA"> </a>

Skype pour Business Web App, d’application de réunions Skype et Skype pour les entreprises pour Mac prend en charge l’authentification multifacteur. Outre le nom d’utilisateur et mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que les cartes à puce ou les codes confidentiels, pour authentifier les utilisateurs qui rejoignent réseaux externes lorsqu’ils se connectent à Skype pour les réunions d’entreprise. Vous pouvez activer l’authentification multifacteur par le déploiement de serveur de fédération Active Directory Federation Services (ADFS) et l’activation de l’authentification passive dans Skype pour Business Server. Après la configuration d’AD FS, les utilisateurs externes qui essaient de participer à Skype pour les réunions d’entreprise sont présentés avec une page Web d’authentification multifacteur AD FS qui contient le nom d’utilisateur et mot de passe défi ainsi que les méthodes d’authentification supplémentaires que vous configurés.

> [!IMPORTANT]
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :

- L'authentification ADFS multifacteur fonctionne si le participant à la réunion et l'organisateur appartiennent à la même organisation ou à une organisation fédérée AD FS. Elle ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web du serveur Lync ne la prend pas en charge pour le moment.

- Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge afin que toutes les demandes provenant du Skype pour les clients professionnels Web App ou application de réunions sont gérés par le même serveur frontal.

- Lorsque vous établissez une confiance entre Skype pour les serveurs Business Server et d’AD FS, affectez une durée de vie de jeton est suffisante pour couvrir la longueur maximale de votre Skype pour les réunions d’entreprise. Une durée de vie de jeton de 240 minutes est généralement suffisante.

- Cette configuration ne s’applique pas aux clients mobiles Lync.

### <a name="configure-multi-factor-authentication"></a>Configuration de l'authentification multifacteur

1. Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, consultez le [Guide de déploiement Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. Créez des certificats pour AD FS. Pour plus d’informations, consultez la section [« Certificats de serveur de fédération »](https://go.microsoft.com/fwlink/p/?LinkId=285376) de la planification pour et déployer AD FS pour une utilisation avec la rubrique ouverture de session unique.

3. À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante :

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. Établissez un partenariat en exécutant la commande suivante :

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. Définissez les règles de partie de confiance suivantes :

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>Désactivation de BranchCache 
<a name="MFA"> </a>

La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec Skype pour les composants WebPart Business Web App. Pour éviter les problèmes de Skype pour les utilisateurs professionnels Web App, assurez-vous que BranchCache n’est pas activé.

Pour plus d’informations sur la désactivation de BranchCache, voir le [Guide de déploiement de BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).

## <a name="verifying-skype-for-business-web-app-deployment"></a>Vérification de Skype pour le déploiement d’applications métiers Web
<a name="MFA"> </a>

Vous pouvez utiliser l'applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l'aide de l'API UCWA (Unified Communications Web API). Pour plus d’informations sur cette applet de commande, voir [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) dans le Skype pour la documentation sur Business Server Management Shell.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Résolution des problèmes d’Installation du plug-in sur Windows Server 2008 R2
<a name="MFA"> </a>

Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Modification du paramètre de sécurité dans Internet Explorer

1. Ouvrez Internet Explorer.

2. Cliquez sur **Outils **, sur **Options Internet **, puis sur **Avancé **.

3. Faites défiler la page vers le bas jusqu'à la section **Sécurité**.

4. Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK **.

    > [!NOTE]
    > Si sélectionné, ce paramètre provoque une erreur lorsque vous tentez de télécharger une pièce jointe à partir de Skype pour l’application Web de gestion.

5. Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.

### <a name="modify-the-disablemsi-registry-setting"></a>Modification du paramètre de Registre DisableMSI

1. Cliquez sur **Démarrer **, puis sur **Exécuter **.

2. Pour accéder à l'Éditeur du registre, tapez **regedit **.

3. Accédez à HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. Modifiez ou ajoutez la clé de Registre DisableMSI de type REG_DWORD, et affectez-lui la valeur 0.

5. Rejoignez la réunion.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Activer l’application de réunions Skype remplacer Skype pour Business Web application (facultatif, Skype pour Business Server 2015 uniquement)
<a name="SMA_Enable"> </a>

Cette procédure est facultative et s’applique à Skype pour Business Server 2015 CU5 et versions ultérieures. Si vous ne l’utilisez pas, les utilisateurs externes continuera à participer à des réunions à l’aide de Skype pour l’application Web de gestion.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>Activation de la participation simplifiée aux réunions et l'application Réunions Skype

1. Lorsque vous activez l’accès pour le réseau CDN (Content Delivery), les utilisateurs auront la possibilité de se connecter CDN en ligne et application de réunions Skype (sous Windows) et Skype pour les entreprises pour Mac (sur Mac) et utilisera simplifié participation de la réunion.

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. Autoriser le client télémétrie de journalisation côté de la réunion de participer à l’application de réunions Skype soient envoyées aux serveurs de Microsoft (la commande false par défaut) ou une page web.

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Les informations envoyées à Microsoft sont en stricte conformité avec [Skype pour entreprise de collecte de données](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).

3. Définir le délai d’attente avant le passage à la Skype hébergé localement pour l’expérience de l’application Web de gestion CDN n’est pas disponible. La valeur par défaut est de 6 secondes. Si celle-ci est définie sur 0, il n'y a pas de délai.

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>Voir aussi
<a name="SMA_Enable"> </a>

[Planifier pour les clients de réunions (application Web et application de réunions)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Configurer la réunion page de participation dans Skype pour Business Server](../../manage/conferencing/meeting-join-page.md)

[Déclaration de confidentialité de Microsoft Online Services](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[Termes du contrat de licence et Documentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

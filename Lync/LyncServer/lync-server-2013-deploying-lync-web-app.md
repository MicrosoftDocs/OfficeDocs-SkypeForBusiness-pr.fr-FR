---
title: Déploiement de Lync Web App
TOCTitle: Déploiement de Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205190(v=OCS.15)
ms:contentKeyID: 49298607
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement de Lync Web App

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Web App est un client web IIS (Internet Information Services) qui s’installe avec Lync Server 2013 et qui est activé par défaut. Aucune étape supplémentaire n’est requise pour activer Lync Web App sur le serveur ou déployer le client web auprès des utilisateurs. Chaque fois qu’un utilisateur clique sur une URL de réunion mais qu’il n’a pas le client Lync 2013 installé, la possibilité de rejoindre la réunion à l’aide de la dernière version de Lync Web App lui est offerte.

Les fonctionnalités vocales, vidéo et de partage de Lync Web App requièrent un contrôle Microsoft ActiveX. Vous pouvez soit installer le contrôle ActiveX à l’avance, soit permettre aux utilisateurs de l’installer lorsqu’ils y sont invités, ce qui est le cas la première fois qu’ils utilisent Lync Web App ou la première fois qu’ils accèdent à une fonctionnalité nécessitant le contrôle ActiveX.

> [!NOTE]  
> Dans les déploiements de serveur Edge Lync Server 2013, un proxy inverse HTTPS dans le réseau de périmètre est requis pour l’accès client Lync Web App. Vous devez également publier des URL simples. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuration des serveurs proxy inverses pour Lync Server 2013</a> et <a href="lync-server-2013-planning-for-simple-urls.md">Planification des URL simples dans Lync Server 2013</a>.

## Activation de l’authentification multifacteur pour Lync Web App

La version Lync Server 2013 de Lync Web App prend en charge l’authentification multifacteur. Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des codes confidentiels, pour authentifier les utilisateurs qui participent depuis des réseaux externes lorsqu’ils se connectent à des réunions Lync. Vous pouvez activer l’authentification multifacteur en déployant un serveur de fédération AD FS (Active Directory Federation Services) et en activant l’authentification passive dans Lync Server 2013. Une fois les services AD FS configurés, une page web d’authentification multifacteur AD FS contenant le nom d’utilisateur et le mot de passe de stimulation, ainsi que toutes les méthodes d’authentification supplémentaires que vous avez configurées s’affiche aux utilisateurs externes qui tentent de rejoindre des réunions Lync.

> [!IMPORTANT]  
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur :<ul>
> <li><p>L’authentification ADFS multifacteur fonctionne si le participant à la réunion et l’organisateur appartiennent à la même organisation ou à une organisation fédérée AD FS. Elle ne fonctionne pas pour les utilisateurs fédérés Lync, car l’infrastructure web du serveur Lync ne la prend pas en charge pour le moment.</p></li>
> <li><p>Si vous utilisez des programmes d’équilibrage de la charge matérielle, activez la persistance des cookies sur les programmes d’équilibrage de la charge afin que toutes les demandes émanant du client Lync Web App soient gérées par le même serveur frontal.</p></li>
> <li><p>Lorsque vous établissez une approbation de la partie de confiance entre Lync Server et les serveurs AD FS, attribuez une durée de vie de jeton suffisamment longue pour couvrir la durée maximale de vos réunions Lync. Une durée de vie de jeton de 240 minutes est généralement suffisante.</p></li>
> <li><p>Cette configuration ne s’applique pas aux clients mobiles Lync.</p></li></ul>


**Pour configurer l’authentification multifacteur**

1.  Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, voir le Guide de déploiement des services AD FS 2.0 à l’adresse [http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x40c)

2.  Créez des certificats pour AD FS. Pour plus d’informations, voir la section « Certificats de serveur de fédération » de l’article « Planifier et déployer AD FS en vue d’une utilisation avec l’authentification unique » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Dans l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante :
    
        add-pssnapin Microsoft.Adfs.powershell

4.  Établissez un partenariat en exécutant la commande suivante :
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Définissez les règles de partie de confiance suivantes :
    
    ```
    $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
    $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
    ```
    
    ```
    Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
    ```
    ```
    Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

## Configuration de la fonctionnalité BranchCache

Dans Windows 7 et Windows Server 2008 R2, la fonctionnalité BranchCache peut interférer avec les composants web Lync Web App. Afin d’éviter que les utilisateurs Lync Web App rencontrent des problèmes, assurez-vous que BranchCache n’est pas activée.

Pour plus d’informations sur la désactivation de BranchCache, voir le Guide de déploiement BranchCache, disponible au format Word dans le Centre de téléchargement Microsoft [http://go.microsoft.com/fwlink/?linkid=268788\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268788%26clcid=0x40c) et au format HTML dans la Bibliothèque technique Windows Server 2008 R2 à l’adresse [http://go.microsoft.com/fwlink/?linkid=268789\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268789%26clcid=0x40c).

## Vérification du déploiement de Lync Web App

Vous pouvez utiliser l’applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l’aide de l’API UCWA (Unified Communications Web API). Pour plus d’informations sur cette applet de commande, voir [Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference) dans la documentation Lync Server Management Shell.

## Résolution des problèmes relatifs à l’installation du plug-in sur Windows Server 2008 R2

Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.

**Pour modifier le paramètre de sécurité dans Internet Explorer**

1.  Ouvrez Internet Explorer.

2.  Cliquez sur **Outils**, sur **Options Internet**, puis sur **Avancé**.

3.  Faites défiler la page vers le bas jusqu’à la section **Sécurité**.

4.  Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > S’il est sélectionné, ce paramètre provoque une erreur lors de la tentative de téléchargement d’une pièce jointe à partir de Lync Web App.

5.  Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.

**Pour modifier le paramètre de Registre DisableMSI**

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Pour accéder à l’Éditeur du Registre, tapez **regedit**.

3.  Accédez à HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.

4.  Modifiez ou ajoutez la clé de Registre DisableMSI de type REG\_DWORD, et affectez-lui la valeur 0.

5.  Rejoignez la réunion.

## Voir aussi

#### Concepts

[Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Plateformes prises en charge par Lync Web App pour Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)


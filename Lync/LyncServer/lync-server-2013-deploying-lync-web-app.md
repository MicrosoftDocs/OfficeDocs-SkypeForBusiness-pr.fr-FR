---
title: 'Lync Server 2013 : déploiement de Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4508c9c499b0219f754bf9815063f4b1210b811
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Déploiement de Lync Web App dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-18_

Lync Web App est un client Web IIS (Internet Information Services) qui est installé avec Lync Server 2013 et est activé par défaut. Aucune étape supplémentaire n’est nécessaire pour activer Lync Web App sur le serveur ou déployer le client Web auprès des utilisateurs. Chaque fois qu’un utilisateur clique sur une URL de réunion mais que le client Lync 2013 n’est pas installé, l’utilisateur est invité à participer à la réunion à l’aide de la dernière version de Lync Web App.

Les fonctionnalités vocales, vidéo et de partage dans Lync Web App nécessitent un contrôle Microsoft ActiveX. Vous pouvez installer le contrôle ActiveX à l’avance ou autoriser les utilisateurs à l’installer lorsque vous y êtes invité, qui se produit lors de la première utilisation de Lync Web App ou lorsqu’il accède pour la première fois à une fonctionnalité nécessitant le contrôle ActiveX.

<div class=" ">


> [!NOTE]  
> Dans les déploiements de serveur Edge Lync Server 2013, un proxy inverse HTTPs dans le réseau de périmètre est requis pour l’accès au client Lync Web App. Vous devez également publier des URL simples. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up proxy inverses for Lync server 2013</A> et <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Activation de l’authentification multifacteur pour Lync Web App

La version Lync Server 2013 de Lync Web App prend en charge l’authentification multifacteur. Outre le nom d’utilisateur et le mot de passe, vous pouvez exiger des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des codes confidentiels, pour authentifier les utilisateurs qui rejoignent des réseaux externes lorsqu’ils se connectent à des réunions Lync. Vous pouvez activer l’authentification multifacteur en déployant le serveur de fédération AD FS (Active Directory Federation Service) et en activant l’authentification passive dans Lync Server 2013. Une fois les services ADFS configurés, les utilisateurs externes qui tentent de participer à des réunions Lync sont présentés avec une page Web d’authentification multifacteur AD FS qui contient le nom d’utilisateur et le mot de passe, ainsi que toutes les autres méthodes d’authentification que vous avez configurées. .

<div class=" ">


> [!IMPORTANT]  
> Vous trouverez ci-dessous des considérations importantes si vous envisagez de configurer les services AD FS pour l’authentification multifacteur : 
> <UL>
> <LI>
> <P>L’authentification multifacteur ADFS fonctionne si le participant à la réunion et l’organisateur sont tous deux dans la même organisation ou s’ils proviennent d’une organisation fédérée AD FS. L’authentification multifacteur ADFS ne fonctionne pas pour les utilisateurs fédérés Lync car l’infrastructure Web Lync Server ne la prend pas en charge actuellement.</P>
> <LI>
> <P>Si vous utilisez des programmes d’équilibrage de la charge matérielle, activez la persistance des cookies sur les programmes d’équilibrage de la charge afin que toutes les demandes du client Lync Web App soient gérées par le même serveur frontal.</P>
> <LI>
> <P>Lorsque vous établissez une approbation de partie de confiance entre les serveurs Lync Server et AD FS, affectez une durée de vie de jeton suffisamment longue pour couvrir la longueur maximale de vos réunions Lync. Une durée de vie de jeton de 240 minutes est généralement suffisante.</P>
> <LI>
> <P>Cette configuration ne s’applique pas aux clients mobiles Lync.</P></LI></UL>



</div>

**Pour configurer l’authentification multifacteur**

1.  Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, consultez le Guide de déploiement des services ADFS (Active Directory Federation Services 2,0) à l’adresse<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  Créer des certificats pour AD FS. Pour plus d’informations, consultez la section « certificats de serveur de Fédération » de la rubrique plan for and Deploy AD FS for use with Single Sign [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)-on.

3.  À partir de l’interface de ligne de commande Windows PowerShell, exécutez la commande suivante :
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  Établissez un partenariat en exécutant la commande suivante :
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Définissez les règles de partie de confiance suivantes :
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>Configuration de la fonctionnalité BranchCache

La fonctionnalité BranchCache dans Windows 7 et Windows Server 2008 R2 peut interférer avec les composants Web de Lync Web App. Pour éviter les problèmes pour les utilisateurs de Lync Web App, assurez-vous que BranchCache n’est pas activé.

Pour plus d’informations sur la désactivation de BranchCache, voir le Guide de déploiement de BranchCache, qui est disponible au format Word [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) dans le centre de téléchargement Microsoft à l’adresse et au format HTML [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)dans la bibliothèque technique de Windows Server 2008 R2 (en anglais) à l’adresse.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Vérification du déploiement de Lync Web App

Vous pouvez utiliser l’applet de commande Test-CsUcwaConference pour vérifier que deux utilisateurs de test peuvent participer à une conférence à l’aide de l’API UCWA (Unified Communications Web API). Pour plus d’informations sur cette applet de commande, voir [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) dans la documentation de Lync Server Management Shell.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Résolution des problèmes d’installation de plug-in sur Windows Server 2008 R2

Si l’installation du plug-in échoue sur un ordinateur exécutant Windows Server 2008 R2, vous devrez peut-être modifier le paramètre de sécurité Internet Explorer ou le paramètre de clé de Registre DisableMSI.

**Pour modifier le paramètre de sécurité dans Internet Explorer**

1.  Ouvrez Internet Explorer.

2.  Cliquez sur **Outils**, sur **Options Internet**, puis sur **Avancé**.

3.  Faites défiler la page vers le bas jusqu’à la section **Sécurité**.

4.  Désactivez la case à cocher **Ne pas enregistrer les pages chiffrées sur le disque**, puis cliquez sur **OK**.
    
    <div class=" ">
    

    > [!NOTE]  
    > Si ce paramètre est sélectionné, un message d’erreur s’affichera également lors de la tentative de téléchargement d’une pièce jointe à partir de Lync Web App.

    
    </div>

5.  Rejoignez la réunion. Le plug-in doit se télécharger sans erreurs.

**Pour modifier le paramètre de Registre DisableMSI**

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Pour accéder à l’Éditeur du Registre, tapez **regedit**.

3.  Naviguez jusqu'\_à\_HKEY\\local\\machine\\Software\\Policies Microsoft Windows\\installer.

4.  Modifiez ou ajoutez la clé de Registre DisableMSI de type\_reg DWORD et affectez-lui la valeur 0.

5.  Rejoignez la réunion.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de la page de participation aux réunions dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)  
[Plateformes de Lync Web App prises en charge pour Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


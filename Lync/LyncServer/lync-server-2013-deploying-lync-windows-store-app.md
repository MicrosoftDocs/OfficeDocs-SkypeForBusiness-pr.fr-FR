---
title: 'Lync Server 2013 : déploiement de l’application Lync du Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef2e96b1e58bb9a92b2dc9748624d38f605965f
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Déploiement de l’application Lync du Windows Store dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-03_

Pour que l’application Lync du Windows Store soit disponible pour les utilisateurs, assurez-vous que votre déploiement répond à la [Configuration requise pour l’application Lync du Windows Store pour Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md). Pour plus d’informations sur la configuration de Lync Server 2013 pour prendre en charge l’application Lync du Windows Store, consultez l’article de blog NextHop, « découverte automatique de Lync Server [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)et l’application Lync du Windows Store ». Une fois votre environnement serveur configuré correctement, vous pouvez indiquer aux utilisateurs de télécharger l’application Lync à partir du Windows Store en effectuant une recherche sur « Lync ».

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Activation de l’authentification multifacteur pour l’application Lync du Windows Store

Mises à jour cumulatives pour Lync Server 2013 : le 2013 de juin ajoute une prise en charge de l’authentification multifacteur pour les clients de l’application Lync du Windows Store. Outre le nom d’utilisateur et le mot de passe, vous pouvez demander des méthodes d’authentification supplémentaires, telles que des cartes à puce ou des épingles, afin d’authentifier les utilisateurs externes lorsque ces personnes se connectent à des réunions Lync. Pour activer l’authentification multifacteur, vous devez déployer le serveur de fédération AD FS (Active Directory Federation Services) et activer l’authentification passive dans Lync Server 2013. Après la configuration d’AD FS, les utilisateurs externes qui essaient de participer à des réunions Lync sont dotés d’une page Web d’authentification multifacteur AD FS contenant le nom d’utilisateur et le mot de passe, ainsi que d’autres méthodes d’authentification que vous avez configurées. .

<div class=" ">


> [!IMPORTANT]  
> Voici quelques points importants à prendre en compte si vous envisagez de configurer AD FS pour l’authentification multifacteur pour l’application Lync du Windows Store : 
> <UL>
> <LI>
> <P>Lync Server 2013 avec des mises à jour cumulatives pour Lync Server 2013:2013 juin est requis au minimum. Les clients de bureau Lync 2013 ne nécessitent pas de mises à jour cumulatives pour Lync Server 2013:2013 de juin, il est donc possible que l’authentification passive fonctionne car les clients Lync 2013 peuvent s’authentifier. Toutefois, le processus d’authentification pour les clients de l’application Lync du Windows Store ne sera pas exécuté et aucune notification ou message d’erreur ne s’affichera.</P>
> <LI>
> <P>Le serveur doit être configuré de manière à ce que l’authentification passive soit le seul type d’authentification offert.</P>
> <LI>
> <P>Si vous utilisez des équilibreurs de charge matérielle, activez la persistance des cookies sur les équilibreurs de charge de sorte que toutes les requêtes du client d’application Lync du Windows Store soient gérées par le même serveur principal.</P>
> <LI>
> <P>Lorsque vous établissez une relation d’approbation de la partie de confiance entre les serveurs Lync Server et AD FS, attribuez une durée de vie du jeton suffisamment longue pour couvrir la longueur maximale de vos réunions Lync. Une durée de vie de jeton de 240 minutes est généralement suffisante.</P></LI></UL>



</div>

**Pour configurer l’authentification multifacteur**

1.  Installez un rôle de serveur de fédération AD FS. Pour plus d’informations, consultez le Guide de déploiement de services ADFS <http://go.microsoft.com/fwlink/p/?linkid=267511>(Active Directory Federation Services) 2,0 à l’adresse.

2.  Créez des certificats pour AD FS. Pour plus d’informations, reportez-vous à la section « certificats de serveur de Fédération » de la rubrique plan pour et déployer AD FS [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)pour une utilisation avec une connexion unique à l’adresse.

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
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>Problèmes connus qui peuvent empêcher la connexion

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>La date et l’heure ne sont pas définies correctement sur l’appareil exécutant l’application Lync du Windows Store

Le paramètre d’heure sur l’appareil doit être synchronisé avec le paramètre d’heure sur le serveur. Ceci est particulièrement important pour les appareils tels que Microsoft surface, et les autres appareils exécutant Windows RT qui ne sont pas joints à un domaine. Pour définir l’heure sur ces appareils automatiquement à partir d’un serveur de temps, exécutez la commande suivante à partir d’une invite de commandes avec élévation de privilèges sur l’appareil :
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>L’application Lync du Windows Store ne peut pas accéder au serveur ou aux services Lync

L’application Lync du Windows Store peut ne pas être en mesure d’accéder au serveur ou aux services Lync par le biais de cartes réseau (par exemple, des modems USB 4G LTE) qui ne s’inscrivent pas sous Windows 8 en tant qu’appareils physiques. L’application Lync du Windows Store peut rencontrer ce problème même lorsque les applications de bureau et les navigateurs sont en mesure d’accéder à d’autres serveurs et sites Web.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>L’application Lync du Windows Store ne peut pas se connecter à l’aide de Lync Server 2010 et d’Office Communications Server 2007 R2 Edge Server

Si votre topologie est composée de Lync Server 2010 avec Office Communications Server 2007 R2 Edge Server, vous devez exécuter la version mise à jour du générateur de topologie disponible dans la mise à jour cumulative pour Lync Server 2010:2013. Les versions antérieures du générateur de topologie ne créent pas le mappage requis pour Office Communications Server 2007 Edge Server, de sorte que les clients de l’application Lync du Windows Store ne peuvent pas se connecter. Les étapes suivantes sont nécessaires :

1.  Installez la mise à jour cumulative pour Lync Server 2010 : juillet 2013 sur les pools 2010 Server et les directeurs Lync Server 2010.

2.  Mettez à jour la configuration de découverte automatique Lync pour indiquer que le point d’entrée SIP externe est l’adresse du serveur Edge en procédant comme suit :
    
    1.  Ouvrez Lync Server Management Shell.
    
    2.  Exécutez la commande suivante :
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>L’application Lync du Windows Store ne peut pas se connecter en raison d’un échec de validation de nom de certificat

Un problème de connexion peut se produire pour les utilisateurs d’Office 365 qui n’exécutent pas la dernière version de l’application Lync du Windows Store. Ce problème se produit généralement lors de l’utilisation de plusieurs domaines (par exemple, lorsque l’URI SIP est **usera@domainZ.com** mais que le serveur de périphérie est **SIP.domainX.com**). Pour résoudre ce problème, les utilisateurs doivent installer la dernière version de l’application Lync du Windows Store, qui nécessite également Windows 8,1.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Utiliser les journaux de l’application Lync du Windows Store pour résoudre les problèmes

Vous pouvez utiliser les journaux générés sur l’appareil pour résoudre les problèmes. Les journaux sont stockés dans le dossier suivant :

% LocalAppData%\\packages\\Microsoft. LyncMX\_8wekyb3d8bbwe\\LocalState\\suivi

Avant de parvenir aux journaux d’un utilisateur, assurez-vous que la journalisation est activée, puis demandez à l’utilisateur d’enregistrer les journaux de manière à ce que toutes les informations stockées en mémoire soient également enregistrées dans les fichiers sur le disque dur.

**Pour activer la journalisation**

1.  Ouvrez l’application Lync du Windows Store sur l’appareil.

2.  Balayez à partir du bord droit de l’écran. Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.

3.  Sélectionnez **paramètres**, cliquez sur **options**, puis configurez les **journaux de diagnostic** sur **activé**.

4.  Si les **journaux de diagnostics** étaient inactifs, vous devez redémarrer Lync. Pour redémarrer Lync, effectuez l’une des opérations suivantes :
    
      - Redémarrez l’appareil.
    
      - Terminez la tâche Lync, puis relancez l’application. Pour mettre fin à la tâche, ouvrez le gestionnaire des tâches Windows, sélectionnez **Lync**, puis appuyez sur **fin de tâche**. Si Lync ne figure pas dans la liste, appuyez sur **plus de détails** et recherchez Lync sous **processus en arrière-plan**.

**Pour enregistrer les journaux**

1.  Ouvrez l’application Lync du Windows Store sur l’appareil.

2.  Essayez de vous connecter.

3.  Balayez à partir du bord droit de l’écran. Si vous utilisez une souris, pointez sur le coin supérieur droit de l’écran, puis déplacez le pointeur de la souris vers le bas de l’écran.

4.  Sélectionnez **paramètres**, sélectionnez **à propos**de, puis **enregistrer les journaux**.

</div>

</div>

<span> </span>

</div>

</div>

</div>


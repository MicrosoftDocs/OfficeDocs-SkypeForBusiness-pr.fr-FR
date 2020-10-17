---
title: 'Lync Server 2013 : configuration de l’authentification passive'
description: 'Lync Server 2013 : configuration de l’authentification passive.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52a83c1413dcac18fb37ff0fe308266a3d7aeab4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548290"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a>Configuration de l’authentification passive Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-11_

La section suivante décrit la configuration de Lync Server 2013 avec des mises à jour cumulatives : juillet 2013 pour prendre en charge l’authentification passive. Une fois activés, les utilisateurs Lync qui sont activés pour l’authentification à deux facteurs doivent utiliser une carte à puce physique ou virtuelle et un code confidentiel valide pour se connecter à l’aide de Lync 2013 avec des mises à jour cumulatives : le client juillet 2013.

<div class="">


> [!NOTE]  
> Il est vivement recommandé aux clients d’activer l’authentification passive pour les services Web et les serveurs d’inscriptions au niveau du service. Si l’authentification passive est activée pour le serveur d’inscriptions et les services Web au niveau global, cela entraînera probablement des échecs d’authentification à l’échelle de l’Organisation pour les utilisateurs qui ne se connectent pas avec la version cumulative de Lync 2013 : client de bureau client de juillet 2013.



</div>

<div>

## <a name="web-service-configuration"></a>Configuration du service Web

Les étapes suivantes décrivent comment créer une configuration de service Web personnalisée pour les directeurs, les pools d’entreprise et les serveurs Standard Edition Server qui seront activés pour l’authentification passive.

**Pour créer une configuration de service Web personnalisée**

1.  Connectez-vous à votre Lync Server 2013 avec des mises à jour cumulatives : le serveur frontal 2013 juillet à l’aide d’un compte d’administrateur Lync.

2.  Lancez Lync Server 2013 Management Shell.

3.  À partir de la ligne de commande Lync Server Management Shell, créez une configuration de service Web pour chaque directeur, pool d’entreprise et serveur Standard Edition Server qui sera activé pour l’authentification passive en exécutant la commande suivante :
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > La valeur du nom de domaine complet WsFedPassiveMetadataUri est le nom du service de Fédération de votre serveur AD FS 2,0. Vous pouvez trouver la valeur nom du service de Fédération dans la console de gestion AD FS 2,0 en cliquant avec le bouton droit de la souris sur <STRONG>service</STRONG> dans le volet de navigation, puis en sélectionnant <STRONG>modifier les propriétés du service de Fédération</STRONG>.

    
    </div>

4.  Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été correctement définies en exécutant la commande suivante :
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification webticket. Pour tous les directeurs, les pools d’entreprise et les serveurs Standard Edition qui seront activés pour l’authentification passive, tous les autres types d’authentification doivent être désactivés dans Lync Web services en exécutant la commande suivante :
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  Vérifiez que tous les autres types d’authentification ont été désactivés avec succès en exécutant la commande suivante :
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Configuration du proxy

Lorsque l’authentification par certificat est désactivée pour les services Web Lync, le client Lync utilise un type d’authentification moins favori, tel que Kerberos ou NTLM, pour s’authentifier auprès du service de serveur d’inscriptions. L’authentification par certificat est toujours nécessaire pour permettre au client Lync de récupérer un webticket, cependant, Kerberos et NTLM doivent être désactivés pour le service de serveur d’inscriptions.

Les étapes suivantes décrivent comment créer une configuration de proxy personnalisée pour les pools Edge, les pools d’entreprise et les serveurs Standard Edition Server qui seront activés pour l’authentification passive.

**Pour créer une configuration de proxy personnalisée**

1.  À partir de la ligne de commande Lync Server Management Shell, créez une configuration de proxy pour chaque Lync Server 2013 avec des mises à jour cumulatives : le pool de serveurs Edge de juillet 2013, le pool d’entreprise et le serveur Standard Edition Server qui seront activés pour l’authentification passive en exécutant les commandes suivantes :
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  Vérifiez que tous les autres types d’authentification proxy ont été désactivés correctement en exécutant la commande suivante :
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Configuration de l’authentification passive de Lync Server
TOCTitle: Configuration de l’authentification passive de Lync Server
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn308569(v=OCS.15)
ms:contentKeyID: 56269635
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’authentification passive de Lync Server

 

_**Dernière rubrique modifiée :** 2013-07-11_

La section suivante décrit la configuration de Lync Server 2013 avec les mises à jour cumulatives de juillet 2013 pour la prise en charge de l’authentification passive. Les utilisateurs de Lync pour lesquels l’authentification à deux facteurs est activée doivent utiliser un lecteur de cartes à puce physiques ou virtuelles et un code confidentiel correct pour se connecter à l’aide du client Lync 2013 avec les mises à jour cumulatives de juillet 2013.

> [!NOTE]  
> Il est fortement recommandé que les clients activent l’authentification passive pour les services Serveur d’inscriptions et web au niveau du service. L’activation au niveau global risquerait en effet de provoquer des échecs d’authentification à l’échelle de l’organisation pour les utilisateurs qui ne se connectent pas avec le client de bureau Lync 2013 avec les mises à jour cumulatives de juillet 2013.

## Configuration de service web

Les étapes suivantes décrivent la création d’une configuration de service web personnalisée pour les directeurs, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.

**Pour créer une configuration de service web personnalisée**

1.  Connectez-vous à votre serveur Lync Server 2013 avec les mises à jour cumulatives de juillet 2013 à l’aide d’un compte d’administrateur de Lync.

2.  Lancez Lync Server 2013 Management Shell.

3.  À partir de la ligne de commande Lync Server Management Shell, créez une configuration de service web pour chaque directeur, pool d’entreprise et serveur Standard Edition pour lequel l’authentification passive sera activée en exécutant la commande suivante :
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    
    > [!WARNING]  
    > La valeur du nom de domaine complet WsFedPassiveMetadataUri correspond au nom du service de fédération de votre serveur AD FS 2.0. Pour consulter la valeur Nom du service de fédération dans la console de gestion AD FS 2.0, cliquez avec le bouton droit sur <strong>Service</strong> dans le volet de navigation, puis sélectionnez <strong>Modifier les propriétés du service de fédération</strong>.

4.  Vérifiez que les valeurs UseWsFedPassiveAuth et WsFedPassiveMetadataUri ont été correctement définies en exécutant la commande suivante :
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  Pour les clients, l’authentification passive est la méthode d’authentification la moins privilégiée pour l’authentification de ticket web. Pour tous les directeurs, pools d’entreprise et serveurs Standard Edition pour lesquels l’authentification passive sera activée, tous les autres types d’authentifications doivent être désactivés dans les services web Lync en exécutant la commande suivante :
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  Vérifiez que tous les autres types d’authentifications ont été correctement désactivés en exécutant la commande suivante :
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

## Configuration de proxy

Si l’authentification par certificat est désactivée pour les services web Lync, le client Lync utilise un type d’authentification moins privilégié, tel que Kerberos ou NTLM, pour l’authentification auprès du service Serveur d’inscriptions. Si l’authentification par certificat est toujours requise pour autoriser le client Lync à récupérer un ticket web, Kerberos et NTLM doivent tout de même être désactivés pour le service Serveur d’inscriptions.

Les étapes suivantes décrivent la création d’une configuration de proxy personnalisée pour les pools Edge, les pools d’entreprise et les serveurs Standard Edition pour lesquels l’authentification passive sera activée.

**Pour créer une configuration de proxy personnalisée**

1.  À partir de la ligne de commande Lync Server Management Shell, créez une configuration de service web pour chaque directeur, pool d’entreprise et serveur Standard Edition Lync Server 2013 avec les mises à jour cumulatives de juillet 2013 pour lequel l’authentification passive sera activée en exécutant les commandes suivantes :
    
    ```
    New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
    -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
    ```
    ```
    New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
    -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
    ```

2.  Vérifiez que tous les autres types d’authentifications proxy ont été correctement désactivés en exécutant la commande suivante :
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth


---
title: "1ères étapes av. début migration des util. de Lync Online vers Lync local"
TOCtitle: "1ères étapes av. début migration des util. de Lync Online vers Lync local"
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62247322
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Premières étapes avant de commencer la migration des utilisateurs de Lync Online vers Lync local

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avant de commencer à déplacer les utilisateurs Lync Online vers votre environnement local, vérifiez que toutes les conditions suivantes sont vraies :

  - Votre environnement local de serveur Lync doit être entièrement déployé et validé. Pour plus d’informations, voir [Déploiement de Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Votre client Lync Online doit être configuré pour l’accès distant PowerShell.
    
    Pour cela, commencez par installer le module Skype Entreprise Online pour Windows PowerShell que vous pouvez vous procurer ici : [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).
    
    Après avoir installé le module, vous pouvez établir une session à distance en tapant l’applet de commande suivante dans le Lync Server Management Shell:
    
    ```
    Import-Module LyncOnlineConnector
    ```
    ```
    $cred = Get-Credential
    ```
    ```
    $CSSession = New-CsOnlineSession -Credential $cred
    ```
    ```
    Import-PSSession $CSSession -AllowClobber
    ```
    
  Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Skype Entreprise Online, voir [Connexion à Lync Online à l’aide de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
  Pour plus d’informations sur l’utilisation du module Skype Entreprise Online PowerShell, voir [Utilisation de Windows PowerShell pour gérer Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Votre Lync Online doit être configuré pour un espace d’adressage SIP partagé. Pour cela, commencez une session Powershell à distance avec Lync Online, puis exécutez l’applet de commande suivante :
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Au terme de ces étapes, vous pouvez passer à [Migration des utilisateurs Lync Online vers Lync local](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).


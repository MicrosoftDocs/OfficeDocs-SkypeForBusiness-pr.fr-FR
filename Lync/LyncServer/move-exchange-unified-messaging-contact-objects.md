---
title: Déplacement des objets de contact de la messagerie unifiée Exchange
TOCTitle: Déplacement des objets de contact de la messagerie unifiée Exchange
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49891307
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement des objets de contact de la messagerie unifiée Exchange

 

_**Dernière rubrique modifiée :** 2012-10-19_

Pour effectuer la migration des objets contact de Standard automatique et d’Accès abonné vers le nouveau déploiement de Lync Server 2013, déplacez au préalable les objets du déploiement Office Communications Server 2007 R2 hérité vers le nouveau déploiement Lync Server 2013 à l’aide des applets de commande **Get-CsExUmContact** et **Move-CsExUmContact**. Sur Exchange Server, exécutez ensuite le script Windows PowerShell**ExchUCUtil** pour que l’action suivante agisse sur le pool Lync récemment déployé :

  - l’ajouter aux passerelles IP de messagerie unifiée ;

  - l’ajouter aux groupes de recherche.

> [!NOTE]  
> Pour utiliser les applets de commande <strong>Get-CsExUmContact</strong> et <strong>Move-CsExUmContact</strong>, vous devez être membre du groupe RTCUniversalUserAdmins et disposer d’une autorisation de l’unité d’organisation dans laquelle les objets contact sont stockés. L’autorisation de l’unité d’organisation peut être accordée à l’aide de l’applet de commande <strong>Grant-OUPermission</strong>.

## Pour déplacer des objets contact dans Lync Server Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Pour chaque pool enregistré avec la messagerie unifiée Exchange (où pool1.contoso.net est un pool du déploiement Office Communications Server 2007 R2 et pool2.contoso.net est le pool du déploiement Lync Server 2013), tapez ce qui suit dans la ligne de commande :
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Pour vérifier que les objets contact sont déplacés, exécutez l’applet de commande **Get-CsExumContact** et confirmez que **RegistrarPool** pointe désormais sur le nouveau pool.

## Pour exécuter le script Windows PowerShell ExchUCUtil

1.  Ouvrez une session sur le serveur de messagerie unifiée Exchange en tant qu’utilisateur disposant des autorisations d’administrateur d’organisation Exchange.

2.  Naviguez jusqu’au script Windows PowerShell ExchUCUtil.
    
    Dans Exchange 2007, ExchUCUtil.ps1 se trouve à l’emplacement suivant : **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**
    
    Dans Exchange 2010, ExchUCUtil.ps1 se trouve à l’emplacement suivant : **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**

3.  Si Exchange est déployé dans une seule forêt, tapez :
    
        exchucutil.ps1
    
    Ou, si Exchange est déployé dans plusieurs forêts, tapez :
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    où *forest FQDN* indique la forêt dans laquelle Lync Server 2013 est déployé.
    
    > [!IMPORTANT]  
    > Veillez à redémarrer le service <strong>Lync Server Front-End</strong> (rtcsrv.exe) <em>après</em> avoir exécuté exchucutil.ps1. Sinon, Lync Server 2013 ne détectera pas la messagerie unifiée dans la topologie.

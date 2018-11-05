---
title: 'Lync Server 2013 : Consignation des affectations de comptes Kerberos'
TOCTitle: Consignation des affectations de comptes Kerberos
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398343(v=OCS.15)
ms:contentKeyID: 49297207
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consignation des affectations de comptes Kerberos dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-01-16_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous pouvez utiliser l’applet de commande **Get-CsKerberosAccountAssignment** pour rechercher des informations sur les affectations de compte d’authentification Kerberos et des informations de rapport sur les affectations actuelles dans votre déploiement.

## Pour rechercher des affectations de compte d’authentification Kerberos pour un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine qui exécute Lync Server 2013 ou sur un ordinateur où les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez l’une des commandes suivantes :
    
      - Pour rechercher toutes les affectations de compte d’authentification Kerberos dans votre organisation et renvoyer les informations d’affectation sur chacune d’entre elles, exécutez l’applet de commande sans aucun paramètre :
        
            Get-CsKerberosAccountAssignment
    
      - Pour rechercher toutes les affectations de compte d’authentification Kerberos dans votre déploiement et renvoyer les informations d’affectation de site sur chacune d’entre elles, exécutez l’applet de commande avec le paramètre Identity :
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Exemple :
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Pour rechercher toutes les affectations de compte d’authentification Kerberos dans un seul site et renvoyer les informations d’affectation sur chacune d’entre elles, exécutez l’applet de commande avec le paramètre Filter :
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Exemple :
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        > [!NOTE]  
        > Si vous spécifiez *SiteName pour le paramètre Filter, le système renvoie les informations sur tous les sites qui contiennent le nom de site spécifié partout dans l’identificateur de site (par exemple, tous les sites qui contiennent la chaîne Redmond dans l’identificateur de site).

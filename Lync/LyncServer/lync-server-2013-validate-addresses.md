---
title: Valider les adresses
TOCTitle: Valider les adresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412808(v=OCS.15)
ms:contentKeyID: 49298483
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Valider les adresses

 

_**Dernière rubrique modifiée :** 2012-09-17_

Avant de publier la base de données des emplacements, vous devez valider les nouveaux emplacements par rapport à la base de données MSAG (Master Street Address Guide) gérée par votre fournisseur de service de jonction SIP ou E9-1-1 PSTN (Public Switched Telephone Network).

Pour plus d’informations sur les fournisseurs de service de E9-1-1 de jonction SIP, voir [Sélection d’un fournisseur de services E9-1-1 pour Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Pour plus d’informations sur la validation des adresses, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

## Pour valider des adresses situées dans la base de données des emplacements

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez les applets de commande suivantes pour configurer la connexion du fournisseur de service d’urgence.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Exécutez l’applet de commande suivante pour valider les adresses de la base de données des emplacements.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.


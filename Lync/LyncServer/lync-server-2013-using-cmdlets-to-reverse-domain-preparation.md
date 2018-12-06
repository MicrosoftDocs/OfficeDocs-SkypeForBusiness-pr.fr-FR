---
title: 'Lync Server 2013 : Utilisation d’applets de commande pour inverser la préparation d’un domaine'
TOCTitle: Utilisation d’applets de commande pour inverser la préparation d’un domaine
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398071(v=OCS.15)
ms:contentKeyID: 49296058
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

Utilisez l’applet de commande **Disable-CsAdDomain** pour inverser l’étape de préparation d’un domaine.

## Pour utiliser des applets de commande afin d’inverser la préparation d’un domaine

1.  Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Exemple :
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Si le paramètre Force est présent, la préparation du domaine est annulée, même si des serveurs frontaux ou des serveurs de conférence A/V dans le domaine sont activés. Si le paramètre Force n’est pas présent, l’annulation de la préparation du domaine s’arrête si des serveurs frontaux ou des serveurs de conférence A/V dans le domaine sont activés.
    
    > [!NOTE]  
    > Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (ce qui est caractéristique des déploiements de mise à niveau pour lesquels le paramètre global n’a pas migré vers le conteneur de configuration), vous devez définir un contrôleur de domaine dans la racine de votre forêt Active Directory. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans les services de domaine Active Directory.


## Voir aussi

#### Tâches

[Exécution de la préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md)  

#### Autres ressources

[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)


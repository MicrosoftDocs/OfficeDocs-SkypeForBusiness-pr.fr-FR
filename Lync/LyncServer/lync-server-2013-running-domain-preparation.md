---
title: 'Lync Server 2013 : Exécution de la préparation du domaine'
TOCTitle: Exécution de la préparation du domaine
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398761(v=OCS.15)
ms:contentKeyID: 49298136
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exécution de la préparation du domaine pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-04-16_

Vous pouvez utiliser le programme d’installation ou des applets de commande Lync Server Management Shell pour préparer des domaines. L’applet de commande qui prépare un domaine est **Enable-CsAdDomain**.

La préparation du domaine est l’étape finale dans la préparation des services de domaine Active Directory pour Lync Server 2013.

## Pour préparer les domaines à l’aide du programme d’installation

1.  Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.

2.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.

3.  Cliquez sur **Préparer Active Directory** , puis attendez que l’état du déploiement soit déterminé.

4.  À l’**Étape 5 : Préparer le domaine actuel** , cliquez sur **Exécuter** .

5.  Dans la page **Préparer le domaine** , cliquez sur **Suivant** .

6.  Dans la page **Exécution de commandes** , recherchez **Statut de la tâche : Terminée** , puis cliquez sur **Afficher le journal** .

7.  Sous la colonne **Action** , développez **Préparation du domaine** , recherchez le résultat d’exécution **\<Opération réussie\>** à la fin de chaque tâche afin de vérifier que la préparation du domaine a abouti, fermez le journal, puis cliquez sur **Terminer** .

8.  Attendez que la réplication d’Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine répertoriés dans le composant logiciel enfichable Sites et services Active Directory pour le contrôleur du domaine racine de la forêt.

## Pour préparer le domaine à l’aide d’applets de commande

1.  Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.

2.  Installez les composants principaux de Lync Server en procédant comme suit :
    
    1.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui** .
    
    3.  La boîte de dialogue Installation de Lync Server 2013 vous invite à indiquer l’emplacement des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer** .
    
    4.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence** , puis cliquez sur **OK** . Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Exécutez :
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Exemple :
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

5.  Vérifiez que la préparation de domaine a été exécutée avec succès. Exécutez :
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Exemple :
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    > [!NOTE]  
    > Le paramètre GlobalSettingsDomainController vous permet d’indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (ce qui est caractéristique des déploiements de mise à niveau qui n’ont pas eu leur paramètre global migré vers le conteneur de configuration), vous définissez un contrôleur de domaine dans la racine de votre forêt Active Directory. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration), vous devez définir un contrôleur de domaine dans la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et indique un contrôleur de domaine dans les services AD DS.    
    Si vous omettez le paramètre **Domain**, le domaine local est utilisé par défaut.
    
    Cette applet de commande renvoie la valeur **LC\_DOMAIN\_SETTINGS\_STATE\_READY** si la préparation du domaine a réussi.

## Voir aussi

#### Tâches

[Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  

#### Autres ressources

[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)


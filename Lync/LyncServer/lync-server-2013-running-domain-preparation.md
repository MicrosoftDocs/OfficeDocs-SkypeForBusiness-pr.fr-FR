---
title: 'Lync Server 2013 : Exécution de la préparation du domaine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fdd01b15fe5858129300c3a9f2f26c3d3de672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Exécution de la préparation du domaine pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-04-16_

Vous pouvez utiliser les applets de applet de configuration ou Lync Server Management Shell pour préparer les domaines. L’applet de cmdlet qui prépare un domaine est **Enable-CsAdDomain**.

La préparation du domaine est l’étape finale de la préparation des services de domaine Active Directory pour Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Pour préparer le domaine à l’aide du programme d’installation

1.  Ouvrez une session sur n’importe quel serveur du domaine en tant que membre du groupe Domain Admins.

2.  À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.

3.  Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

4.  À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.

5.  Dans la page **préparer le domaine** , cliquez sur **suivant**.

6.  Dans la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

7.  Dans la colonne **action** , développez **Domain PREP**, recherchez un ** \<résultat\> ** d’exécution réussie à la fin de chaque tâche pour vérifier que la préparation du domaine s’est déroulée correctement, fermez le journal, puis cliquez sur **Terminer**.

8.  Attendez la fin de la réplication Active Directory pour qu’elle soit terminée ou forcée de réplication à tous les contrôleurs de domaine figurant dans le composant logiciel enfichable sites et services Active Directory pour le contrôleur de domaine racine de la forêt.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Pour utiliser des applets de cmdlet pour préparer le domaine

1.  Ouvrez une session sur n’importe quel serveur du domaine en tant que membre du groupe Domain Admins.

2.  Installez les composants principaux de Lync Server comme suit:
    
    1.  À partir du dossier d’installation ou du média de Lync Server 2013, exécutez Setup. exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.
    
    3.  La boîte de dialogue de configuration de Lync Server 2013 vous invite à entrer un emplacement d’installation des fichiers du serveur Lync. Choisissez l’emplacement par défaut **** ou naviguez jusqu’à l’emplacement de votre choix, puis cliquez sur **installer**.
    
    4.  Sur la page contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Exécutez :
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Par exemple :
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le Domain local.

5.  Vérifiez que la préparation du domaine a réussi. Exécutez :
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Par exemple :
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Le paramètre GlobalSettingsDomainController vous permet d’indiquer l’emplacement de stockage des paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (qui est courant pour les déploiements de mise à niveau qui n’ont pas été migrés vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt Active Directory. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous devez définir un contrôleur de domaine dans la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et font référence à tout&nbsp;contrôleur de domaine dans AD DS.

    
    </div>
    
    Si vous ne spécifiez pas le paramètre **Domain** , la valeur par défaut est le Domain local.
    
    Cette applet de cmdlet renvoie une valeur de la fonction **\_DOMAINSETTINGS\_\_**

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Utilisation d’applets de commande pour inverser la préparation d’un domaine pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


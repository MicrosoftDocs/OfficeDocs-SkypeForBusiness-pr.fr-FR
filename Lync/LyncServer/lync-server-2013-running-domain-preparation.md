---
title: 'Lync Server 2013 : exécution de la préparation du domaine'
description: 'Lync Server 2013 : exécution de la préparation du domaine.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2c4ebe94d07ed2d1fd9be013cd8e88204312f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577780"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a>Exécution de la préparation du domaine pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-04-16_

Vous pouvez utiliser le programme d’installation ou les applets de commande Lync Server Management Shell pour préparer les domaines. L’applet de commande qui prépare un domaine est **Enable-CsAdDomain**.

La préparation du domaine est la dernière étape de la préparation des services de domaine Active Directory pour Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Pour préparer les domaines à l’aide du programme d’installation

1.  Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.

2.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.

3.  Cliquez sur **Préparer Active Directory**, puis attendez que l’état du déploiement soit déterminé.

4.  À l’**Étape 5 : Préparer le domaine actuel**, cliquez sur **Exécuter**.

5.  Sur la page **préparer le domaine** , cliquez sur **suivant**.

6.  Sur la page **Exécution de commandes**, recherchez **Statut de la tâche : Terminée**, puis cliquez sur **Afficher le journal**.

7.  Sous la colonne **action** , développez **préparation du domaine**, recherchez un résultat d' **\<Success\>** exécution à la fin de chaque tâche pour vérifier que la préparation du domaine s’est correctement effectuée, fermez le journal, puis cliquez sur **Terminer**.

8.  Attendez que la réplication Active Directory soit terminée ou forcez la réplication sur tous les contrôleurs de domaine figurant dans le composant logiciel enfichable sites et services Active Directory pour le contrôleur de domaine racine de la forêt.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Pour préparer le domaine à l’aide de cmdlets

1.  Ouvrez une session sur un serveur dans le domaine en tant que membre du groupe Administrateurs de domaine.

2.  Installez les composants principaux de Lync Server comme suit :
    
    1.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si le système vous invite à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui**.
    
    3.  La boîte de dialogue Configuration de Lync Server 2013 vous invite à indiquer un emplacement d’installation des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer**.
    
    4.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence**, puis cliquez sur **OK**. Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

4.  Générer
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Par exemple :
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

5.  Vérifiez que la préparation du domaine a réussi. Générer
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Par exemple :
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Le paramètre GlobalSettingsDomainController vous permet d'indiquer où sont stockés les paramètres globaux. Si vos paramètres sont stockés dans le conteneur système (ce qui est normal dans les déploiements de mise à niveau dont les paramètres globaux n’ont pas été migrés vers le conteneur de configuration), vous définissez un contrôleur de domaine à la racine de votre forêt Active Directory. Si les paramètres globaux se trouvent dans le conteneur de configuration (ce qui est caractéristique des nouveaux déploiements ou des déploiements de mise à niveau où les paramètres ont été migrés vers le conteneur de configuration, vous définissez tout contrôleur de domaine de la forêt. Si vous ne spécifiez pas ce paramètre, l’applet de commande suppose que les paramètres sont stockés dans le conteneur de configuration et font référence à n’importe quel contrôleur de domaine dans AD &nbsp; DS.

    
    </div>
    
    Si vous ne spécifiez pas le paramètre **Domain** , la valeur par défaut est le domaine local.
    
    Cette applet de commande renvoie une valeur de **LC \_ DOMAINSETTINGS \_ State \_ Ready** si la préparation du domaine a réussi.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Utilisation d’applets de commande pour inverser la préparation du domaine pour Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


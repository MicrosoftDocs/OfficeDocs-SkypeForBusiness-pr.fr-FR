---
title: Déploiement des régions réseau, des sites réseau et des sous-réseaux dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Créer ou modifier des régions réseau, sites réseau et associer des sous-réseaux dans Skype pour Business Server. Tous ces sont utilisés pour les fonctionnalités voix entreprise : le contournement de média, appel de contrôle d’admission des appels et le routage basé sur l’emplacement.'
ms.openlocfilehash: 39fb65f3f2bef0ab81833b42fe50cbf866bee65b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568381"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business-2015"></a>Déploiement des régions réseau, des sites réseau et des sous-réseaux dans Skype Entreprise 2015
 
Créer ou modifier des régions réseau, sites réseau et associer des sous-réseaux dans Skype pour Business Server. Tous ces sont utilisés pour les fonctionnalités voix entreprise : le contournement de média, appel de contrôle d’admission des appels et le routage basé sur l’emplacement.
  
Les fonctionnalités avancées de Voix Entreprise sont [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md) et [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Ces fonctionnalités tous les exigent que vous permet de créer des régions réseau, sites réseau et sous-réseaux. Par exemple, toutes ces fonctionnalités requièrent que chaque sous-réseau de votre topologie soit associé à un site réseau spécifique, et que chaque site réseau soit associé à une région réseau. Pour plus d’informations sur ces conditions, voir [paramètres réseau pour les fonctionnalités Enterprise Voice dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)
  
Le contrôle d’admission des appels et E9-1-1 ont des exigences de configuration supplémentaires pour les sites réseau :
  
- Contrôle d’admission des appels implique de spécifier un profil de stratégie de bande passante pour chaque site qui est limité par des restrictions de bande passante WAN. Si vous prévoyez de déployer le contrôle d’admission des appels d’appel, vous devez[créer des profils de stratégie de bande passante dans Skype pour Business Server 2015](create-bandwidth-policy-profiles.md) avant de configurer vos sites réseau.
    
- E9-1-1 implique de spécifier une stratégie d’emplacement pour chaque site. Si vous prévoyez de déployer E9-1-1, vous devez[créer les stratégies d’emplacement dans Skype pour Business Server 2015](create-location-policies.md) avant de configurer vos sites réseau.
    
## <a name="create-or-modify-a-network-region"></a>Créer ou modifier une région réseau

Si vous avez déjà créé des régions réseau pour une de ces fonctionnalités, il est inutile créer de nouvelles régions de réseau ; autres fonctionnalités voix entreprise utilisera ces mêmes zones réseau. 
  
Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central. 
  
### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Pour créer une région de réseau à l’aide de Skype pour Business Server Management Shell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande New-CsNetworkRegion pour créer des régions réseau :
    
   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Exemple :
    
   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    Dans cet exemple, vous avez créé une région réseau appelée « NorthAmerica » qui est associé à un site central avec l’ID de site CHICAGO.
    
3. Pour finir de créer des régions réseau pour votre topologie, répétez l’étape 2 avec des paramètres pour chaque région réseau.
    
### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Pour créer une région de réseau à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur **Région**.
    
4. Cliquez sur **Nouveau**.
    
5. Dans la page **Nouvelle région**, cliquez sur **Nom**, puis tapez le nom de la région réseau.
    
6. Cliquez sur **Site central**, puis cliquez sur un site central dans la liste.
    
7. Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.
    
8. Cliquez sur **Valider**.
    
9. Pour finir de créer des régions réseau pour votre topologie, répétez les étapes 4 à 8 avec des paramètres pour d’autres régions.
    
### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Pour modifier une région réseau à l’aide de Skype pour Business Server Management Shell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande Set-CsNetworkRegion pour modifier une région réseau existante :
    
   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Exemple :
    
   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    Dans cet exemple, vous avez modifié une région réseau existante appelée « NorthAmerica » (créé en utilisant les procédures décrites précédemment dans cette rubrique) en modifiant la description. S’il existait une description pour la région « NorthAmerica », cette commande remplace avec cette valeur ; Si aucune description n’a été définie, cette commande définit son.
    
3. Pour modifier d’autres régions réseau, répétez l’étape 2 avec les paramètres d’autres régions.
    
### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Pour modifier une région réseau à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Région**.
    
4. Dans le tableau, cliquez sur la région réseau que vous souhaitez modifier.
    
5. Cliquez sur **Modifier**, puis sur **Afficher les détails…**.
    
6. Dans la page **Modifier la région** , changez les valeurs pour les paramètres de cette région réseau comme il convient.
    
7. Cliquez sur **Valider**.
    
8. Pour finir de modifier les régions réseau, répétez les étapes 4 à 7 avec des paramètres pour d’autres régions.
    
## <a name="create-or-modify-a-network-site"></a>Création ou modification d’un site réseau

Si vous avez déjà créé des sites réseau pour une de ces fonctionnalités, il est inutile créer des sites de réseau ; autres fonctionnalités voix entreprise utilisera ces mêmes sites réseau. Cependant, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante. 
  
### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Pour créer un site réseau à l’aide de Skype pour Business Server Management Shell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :
    
   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Exemple :
    
   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    Dans cet exemple, vous avez créé un site réseau appelé « Chicago » qui se trouve dans la région « NorthAmerica ».
    
    > [!NOTE]
    > La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement. 
  
3. Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.
    
### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Pour créer un site réseau à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Site**.
    
4. Cliquez sur **Nouveau**.
    
5. Dans la page **Nouveau site**, cliquez sur **Nom**, puis tapez le nom du site réseau.
    
6. Cliquez sur **Région**, puis cliquez sur une région dans la liste.
    
7. Éventuellement, cliquez sur **Stratégie de bande passante**, puis sur une stratégie de bande passante dans la liste.
    
    > [!NOTE]
    > La stratégie de bande passante est uniquement requise si vous déployez le contrôle d’admission des appels sur le site. 
  
8. Éventuellement, cliquez sur **Stratégie d’emplacement**, puis sur une stratégie d’emplacement dans la liste.
    
    > [!NOTE]
    > La stratégie d’emplacement est uniquement requise si vous déployez le système E9-1-1 sur le site. 
  
9. Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.
    
10. Cliquez sur **Valider**.
    
11. Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.
    
### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Pour modifier un site réseau à l’aide de Skype pour Business Server Management Shell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :
    
   ```
   Set-CsNetworkSite -Identity <string>
   ```

    Exemple :
    
   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    Dans cet exemple, le site appelé « Albuquerque » est déplacé vers la région « NorthAmerica ». Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.
    
    > [!NOTE]
    > Même si le paramètre BypassID existe pour la déviation du trafic multimédia, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour la déviation du trafic multimédia. 
  
3. Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.
    
### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Pour modifier un site réseau à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Site**.
    
4. Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.
    
5. Cliquez sur **Modifier**, puis sur **Afficher les détails…**.
    
6. Dans la page **Modifier le Site** , changez les valeurs des paramètres de ce site réseau comme il convient.
    
7. Cliquez sur **Valider**.
    
8. Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.
    
## <a name="associate-a-subnet-with-a-network-site"></a>Association d’un sous-réseau à un site réseau
<a name="BKMK_AssociateSubnets"> </a>

Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique, car les informations de sous-réseau servent à définir le site réseau sur lequel figure un point de terminaison lorsqu’une nouvelle session est initiée. Lorsque vous connaissez l’emplacement de chaque partie dans une session, advanced Enterprise Voice fonctionnalités peuvent s’appliquer ces informations pour déterminer comment gérer la configuration des appels ou de routage.
  
Toutes les adresses IP publiques configurées des serveurs Edge audio/vidéo de votre déploiement doivent être ajoutées à vos paramètres de configuration réseau. Ces adresses IP sont ajoutées sous forme de sous-réseaux avec un masque de 32. Le site réseau associé doit correspondre au site réseau configuré approprié. Par exemple, l’adresse IP publique qui correspond à A / service V Edge dans un site central Chicago serait NetworkSiteID Chicago.
  
### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Pour associer un sous-réseau à un site réseau à l’aide de Skype pour Business Server Management Shell

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez l’applet de commande **New-CsNetworkSubnet** pour associer un sous-réseau à un site réseau :
    
   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Par exemple :
     
   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    Dans cet exemple, vous avez créé une association entre le sous-réseau 172.11.12.13 et le site réseau « Chicago ».
    
3. Répétez l’étape 2 pour tous les sous-réseaux de votre topologie.
    
### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Pour associer des sous-réseaux à des sites réseau en important un fichier CSV

1. Créez un fichier CSV incluant tous les sous-réseaux que vous souhaitez ajouter. Par exemple, créez un fichier **subnet.csv** avec le contenu suivant :
    
     `IPAddress, mask, description, NetworkSiteID`
    
     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Exécutez la cmdlet suivante pour importer **le fichier subnet.csv**, puis enregistrez son contenu dans le magasin de gestion de Lync Server :
    
   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Pour associer un sous-réseau à un site réseau à l’aide de Skype pour Business Server Control Panel

1. Ouvrez le panneau de configuration serveur Business Skype.
    
2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.
    
3. Cliquez sur le bouton de navigation **Sous-réseau**.
    
4. Cliquez sur **Nouveau**.
    
5. Dans la page **Nouveau sous-réseau**, cliquez sur **ID de sous-réseau**, puis entrez la première adresse de la plage d’adresses IP définie par le sous-réseau que vous souhaitez associer à un site réseau.
    
6. Cliquez sur **Masque**, puis entrez le masque de bits à appliquer au sous-réseau.
    
7. Cliquez sur **ID de site réseau**, puis sélectionnez l’ID du site auquel vous ajoutez ce sous-réseau.
    
    > [!NOTE]
    > Si vous n’avez pas encore créé de sites réseau, cette liste est vide. Pour plus d’informations sur la procédure, voir [créer ou modifier un Site réseau](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx). Vous pouvez également récupérer l’ID de site pour votre déploiement en exécutant l’applet de commande **Get-CsNetworkSite** . Pour plus d’informations, voir le Skype pour la documentation sur Business Server Management Shell.
  
8. Éventuellement, cliquez sur **Description**, puis entrez des informations supplémentaires pour décrire ce sous-réseau.
    
9. Cliquez sur **Valider**.
    
Répétez ces étapes pour ajouter d’autres sous-réseaux à un site réseau.
> [!NOTE]
> Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de huit heures. 
  
Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :
  
 **Source** : Service de stratégie de bande passante (principal) CS 
  
 **Numéro d’événement** : 36034
  
 **Niveau** : 2
  
 **Description**: les sous-réseaux pour les adresses IP suivantes : \<liste d’adresses IP\> ne sont pas configurés ou les sous-réseaux ne sont pas associés à un Site réseau. 
  
 **Cause** : les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau. 
  
 **Résolution** : ajoutez aux paramètres de configuration réseau les sous-réseaux correspondant à la liste des adresses IP et associez chaque sous-réseau à un site réseau.
  
Par exemple, si la liste d’adresses IP qui s’affiche dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :
  
1. Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.
    
2. Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.
    
## <a name="see-also"></a>Voir aussi
<a name="BKMK_AssociateSubnets"> </a>

[Nouvelle-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)
  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)
  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)
  
[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)
  
[Nouvelle-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)
  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)
  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)
  
[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)
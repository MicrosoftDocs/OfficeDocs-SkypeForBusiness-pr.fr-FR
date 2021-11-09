---
title: Déployer des régions réseau, des sites et des sous-réseaux dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Créez ou modifiez des régions réseau, des sites réseau et associez des sous-réseaux dans Skype Entreprise Server. Toutes ces fonctionnalités sont utilisées pour les fonctionnalités Voix Entreprise avancées : déviation du média, contrôle d’admission des appels et routage géolocal.'
ms.openlocfilehash: 4d726466153f30b7c5fdd3ac478b1b2444838ae6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856301"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>Déployer des régions réseau, des sites et des sous-réseaux dans Skype Entreprise

Créez ou modifiez des régions réseau, des sites réseau et associez des sous-réseaux dans Skype Entreprise Server. Toutes ces fonctionnalités sont utilisées pour les fonctionnalités Voix Entreprise avancées : déviation du média, contrôle d’admission des appels et routage géolocal.

Les fonctionnalités Voix Entreprise avancées sont le contrôle [d’admission](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)des [appels,](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)le contournement de média, le [routage](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)basé sur l’emplacement et [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md). Ces fonctionnalités nécessitent toutes la création de régions réseau, de sites réseau et de sous-réseaux. Par exemple, toutes ces fonctionnalités nécessitent que chaque sous-réseau de votre topologie soit associé à un site réseau spécifique, et que chaque site réseau soit associé à une région réseau. Pour plus d’informations sur ces termes, voir Paramètres réseau pour les [fonctionnalités Voix Entreprise avancées dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).

Le contrôle d’admission des appels et E9-1-1 ont des exigences de configuration supplémentaires pour les sites réseau :

- Le contrôle d’admission des appels nécessite de spécifier un profil de stratégie de bande passante pour chaque site soumis à des restrictions de bande passante de réseau étendu (WAN). Si vous envisagez de déployer le contrôle d’admission des appels, vous devez créer des profils de stratégie de bande passante [Skype Entreprise Server](create-bandwidth-policy-profiles.md) avant de configurer vos sites réseau.

- E9-1-1 nécessite de spécifier une stratégie d’emplacement pour chaque site. Si vous prévoyez de déployer E9-1-1, vous devez créer des stratégies d’emplacement Skype Entreprise Server avant de configurer vos sites réseau. [](create-location-policies.md)

## <a name="create-or-modify-a-network-region"></a>Créer ou modifier une région réseau

Si vous avez déjà créé des régions réseau pour l’une de ces fonctionnalités, vous n’avez pas besoin de créer de nouvelles régions réseau . d’autres fonctionnalités Voix Entreprise avancées utiliseront ces mêmes régions réseau.

Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis déployez ensuite le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>Pour créer une région réseau à l’aide Skype Entreprise Server Management Shell

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

2. Exécutez l’applet de commande New-CsNetworkRegion pour créer des régions réseau :

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Par exemple :

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    Dans cet exemple, vous avez créé une région réseau appelée « NorthAmerica » qui est associée à un site central avec l’ID de site CHICAGO.

3. Pour finir de créer des régions réseau pour votre topologie, répétez l’étape 2 avec des paramètres pour chaque région réseau.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>Pour créer une région réseau à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3. Cliquez sur **Région**.

4. Cliquez sur **Nouveau**.

5. Dans la page **Nouvelle région**, cliquez sur **Nom**, puis tapez le nom de la région réseau.

6. Cliquez sur **Site central**, puis cliquez sur un site central dans la liste.

7. Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.

8. Cliquez sur **Valider**.

9. Pour finir de créer des régions réseau pour votre topologie, répétez les étapes 4 à 8 avec des paramètres pour d’autres régions.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>Pour modifier une région réseau à l’aide de Skype Entreprise Server Management Shell

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

2. Exécutez l’applet de commande Set-CsNetworkRegion pour modifier une région réseau existante :

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    Par exemple :

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    Dans cet exemple, vous avez modifié une région réseau existante appelée « NorthAmerica » (créée à l’aide des procédures plus tôt dans cette rubrique) en modifiant la description. Si une description existait pour la région « NorthAmerica », cette commande la réécrit avec cette valeur . si aucune description n’a été définie, cette commande la définit.

3. Pour modifier d’autres régions réseau, répétez l’étape 2 avec les paramètres d’autres régions.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>Pour modifier une région réseau à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3. Cliquez sur le bouton de navigation **Région**.

4. Dans le tableau, cliquez sur la région réseau que vous souhaitez modifier.

5. Cliquez sur **Modifier**, puis sur **Afficher les détails…**.

6. Dans la page **Modifier la** région, modifiez les valeurs des paramètres de cette région réseau, le cas échéant.

7. Cliquez sur **Valider**.

8. Pour finir de modifier les régions réseau, répétez les étapes 4 à 7 avec des paramètres pour d’autres régions.

## <a name="create-or-modify-a-network-site"></a>Créer ou modifier un site réseau

Si vous avez déjà créé des sites réseau pour l’une de ces fonctionnalités, vous n’avez pas besoin de créer de nouveaux sites réseau . d’autres fonctionnalités Voix Entreprise avancées utiliseront ces mêmes sites réseau. Toutefois, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>Pour créer un site réseau à l’aide de Skype Entreprise Server Management Shell

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

2. Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    Par exemple :

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    Dans cet exemple, vous avez créé un site réseau appelé « Chicago » qui se trouve dans la région réseau « NorthAmerica ».

    > [!NOTE]
    > La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement.

3. Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>Pour créer un site réseau à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.

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

11. Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>Pour modifier un site réseau à l’aide de Skype Entreprise Server Management Shell

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

2. Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    Par exemple :

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    Dans cet exemple, le site appelé « Albuquerque » est déplacé vers la région réseau « NorthAmerica ». Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.

    > [!NOTE]
    > Bien que le paramètre BypassID existe pour le contournement de média, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour le contournement de média.

3. Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>Pour modifier un site réseau à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3. Cliquez sur le bouton de navigation **Site**.

4. Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.

5. Cliquez sur **Modifier**, puis sur **Afficher les détails…**.

6. Dans la page **Modifier le site,** modifiez les valeurs des paramètres de ce site réseau, le cas échéant.

7. Cliquez sur **Valider**.

8. Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.

## <a name="associate-a-subnet-with-a-network-site"></a>Associer un sous-réseau à un site réseau
<a name="BKMK_AssociateSubnets"> </a>

Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique, car les informations de sous-réseau servent à définir le site réseau sur lequel figure un système d’extrémité lorsqu’une nouvelle session est initiée. Lorsque l’emplacement de chaque partie dans une session est connu, les fonctionnalités Voix Entreprise avancées peuvent appliquer ces informations pour déterminer comment gérer la configuration ou le routage des appels.

Toutes les adresses IP publiques configurées des serveurs Edge audio/vidéo de votre déploiement doivent être ajoutées à vos paramètres de configuration réseau. Ces adresses IP sont ajoutées sous forme de sous-réseaux avec un masque de 32. Le site réseau associé doit correspondre au site réseau configuré approprié. Par exemple, l’adresse IP publique qui correspond au service Edge A/V dans le site central Chicago serait NetworkSiteID Chicago.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>Pour associer un sous-réseau à un site réseau à l’aide de Skype Entreprise Server Management Shell

1. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

2. Exécutez l’applet de commande **New-CsNetworkSubnet** pour associer un sous-réseau à un site réseau :

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    Par exemple :

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    Dans cet exemple, vous avez créé une association entre le sous-réseau 172.11.12.13 et le site réseau « Chicago ».

3. Répétez l’étape 2 pour tous les sous-réseaux de votre topologie.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Pour associer des sous-réseaux à des sites réseau en important un fichier CSV

1. Créez un fichier CSV incluant tous les sous-réseaux que vous souhaitez ajouter. Par exemple, créez un fichier **subnet.csv** avec le contenu suivant :

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

3. Exécutez l’cmdlet suivante pour importer **subnet.csv,** puis stockez son contenu dans le magasin de gestion Lync Server :

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>Pour associer un sous-réseau à un site réseau à l’aide du Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.

3. Cliquez sur le bouton de navigation **Sous-réseau**.

4. Cliquez sur **Nouveau**.

5. Dans la page **Nouveau sous-réseau**, cliquez sur **ID de sous-réseau**, puis entrez la première adresse de la plage d’adresses IP définie par le sous-réseau que vous souhaitez associer à un site réseau.

6. Cliquez sur **Masque**, puis entrez le masque de bits à appliquer au sous-réseau.

7. Cliquez sur **ID de site réseau**, puis sélectionnez l’ID du site auquel vous ajoutez ce sous-réseau.

    > [!NOTE]
    > Si vous n’avez pas encore créé de sites réseau, cette liste est vide. Pour plus d’informations sur la procédure, voir [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site). Vous pouvez également récupérer des ID de site pour votre déploiement en exécutant l’applet de commande **Get-CsNetworkSite**. Pour plus d’informations, voir la documentation Skype Entreprise Server Management Shell.

8. Éventuellement, cliquez sur **Description**, puis entrez des informations supplémentaires pour décrire ce sous-réseau.

9. Cliquez sur **Valider**.

Répétez ces étapes pour ajouter d’autres sous-réseaux à un site réseau.
> [!NOTE]
> Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de huit heures.

Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :

 **Source** : service de stratégie de bande passante CS (principal)

 **Numéro d’événement** : 36034

 **Niveau** : 2

 **Description**: les sous-réseaux pour les adresses IP suivantes : ne sont pas configurés ou les sous-réseaux ne sont pas \<List of IP Addresses\> associés à un site réseau.

 **Cause** : les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.

 **Résolution** : ajoutez aux paramètres de configuration réseau les sous-réseaux correspondant à la liste des adresses IP et associez chaque sous-réseau à un site réseau.

Par exemple, si la liste d’adresses IP qui apparaît dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :

1. Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.

2. Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.

## <a name="see-also"></a>Voir aussi
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)
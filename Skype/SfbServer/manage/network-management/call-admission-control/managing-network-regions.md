---
title: Gestion des régions réseau
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Région réseau * sont les concentrateurs réseau ou des dorsales principales utilisées dans la configuration de contournement des médias, E9-1-1 et contrôle d’admission des appels appel.
ms.openlocfilehash: 3fe6707e6949fa47a9cc5e96703e06132ed8cb2f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223310"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gestion des régions réseau dans Skype pour Business Server

*Régions réseau* sont les concentrateurs réseau ou des dorsales principales utilisées dans la configuration de contournement des médias, E9-1-1 et contrôle d’admission des appels appel. Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau. Par exemple, si vous avez déjà créé des régions réseau pour une fonctionnalité de voix, il est inutile créer de nouvelles régions de réseau ; autres fonctionnalités voix entreprise utilisera ces mêmes zones réseau. Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central. 

Utilisez les procédures dans cet article pour afficher les informations de région de réseau ou créer, modifier ou supprimer des régions de réseau. 

## <a name="view-network-region-information"></a>Afficher les informations de région réseau 


Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel s’exécute le service de stratégie de bande passante appel d’admission des appels (CAC) de contrôle. Vous pouvez utiliser Skype pour Business Server Control Panel pour afficher les régions de réseau. Régions de réseau incluent les paramètres qui déterminent si les autres chemins via Internet sont autorisés pour les connexions audio et vidéos. Utilisez cette rubrique pour afficher des régions réseau existantes. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Pour afficher des informations sur une région de réseau avec Skype pour Business Server Control Panel

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.

4.  Dans la page **région** , cliquez sur la région que vous souhaitez afficher.
  
    > [!NOTE]  
    > Vous ne pouvez afficher qu’une région à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de région réseau à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les informations de région réseau à l’aide de Windows PowerShell et l’applet de commande **Get-CsNetworkRegion** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Pour afficher les informations de région réseau

  - Pour afficher des informations sur toutes les régions de votre réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :
    
        Get-CsNetworkRegion
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Créer ou modifier des régions réseau 

Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel s’exécute le service de stratégie de bande passante appel d’admission des appels (CAC) de contrôle. Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les régions de réseau. Régions de réseau incluent les paramètres qui déterminent si les autres chemins via Internet sont autorisés pour les connexions audio et vidéos. À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer une région réseau. Utilisez cette rubrique pour créer et modifier des régions réseau. 

### <a name="to-create-a-network-region"></a>Pour créer une région de réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.

4.  Dans la page **région** , cliquez sur **Nouveau**.

5.  Dans la page **Nouvelle région** , tapez une valeur dans le champ **nom** . Cette valeur doit être unique au sein de votre Skype pour le déploiement de serveur d’entreprise.

6.  Dans la liste déroulante **site Central** , sélectionnez le site central pour cette région réseau.

7.  La case à cocher **Activer le chemin d’accès de substitution audio** est activée par défaut. Ce champ détermine si les appels audio seront acheminés via un chemin alternatif si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin désactiver le déchargement vers Internet. Si certains de vos appels seront des appels Internet, cette case à cocher doit être activée, quel que soit les paramètres de bande passante.

8.  La case à cocher **Activer le chemin d’accès de substitution vidéo** est activée par défaut. Ce champ détermine si les appels vidéo seront acheminés via un chemin alternatif si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin désactiver le déchargement vers Internet. Si certains de vos appels seront des appels Internet, cette case à cocher doit être activée, quel que soit les paramètres de bande passante.

9.  (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région ne suffit pas au nom seul.

10. Cliquez sur **Valider**.

La table **sites associés** n’est pas utilisée pour la création d’une région de réseau. Vous associez un site à une région lorsque vous créez ou modifiez le site. Pour plus d’informations, voir [Managing le contrôle d’admission des appels d’appel pour les sites](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Pour modifier une région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.

4.  Dans la page **région** , cliquez sur la région que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier la région** , vous pouvez modifier les paramètres d’activation et désactivation des paramètres audio / vidéo des chemins d’accès de substitution et modifier la description (pour plus d’informations, consultez la section « pour créer une région réseau » plus haut dans cette rubrique.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie pour référence et vous connaissez les sites qui seront affectés lorsque vous modifiez les paramètres de zone.


## <a name="delete-existing-network-regions"></a>Supprimer des régions réseau existantes 

Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques. Chaque région réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel s’exécute le service de stratégie de bande passante appel d’admission des appels (CAC) de contrôle. Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les régions de réseau. Régions de réseau incluent les paramètres qui déterminent si les autres chemins via Internet sont autorisés pour les connexions audio et vidéos. À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer une région réseau. Utilisez cette rubrique pour supprimer des régions réseau existantes. 

### <a name="to-delete-a-network-region"></a>Pour supprimer une région réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.

4.  Dans la page **région** , cliquez sur la région que vous souhaitez supprimer.
  
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs régions à la fois. Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs régions tout en maintenant la touche CTRL enfoncée. Ou, pour sélectionner toutes les régions, cliquez sur **Sélectionner tout** dans le menu **Edition** .

5.  Dans le menu **Edition** , cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.


    > [!WARNING]  
    > Une région de réseau ne peut pas être supprimée si elle est associée à un site réseau. Si vous tentez de supprimer une région associée à un site, vous recevrez un message d’erreur. Pour voir si une région est associée à tous les sites, sélectionnez la région, puis sur **Afficher les détails** dans le menu **Edition** .


## <a name="see-also"></a>Voir aussi

[Gestion des itinéraires de région réseau](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
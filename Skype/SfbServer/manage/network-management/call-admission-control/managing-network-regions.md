---
title: Gestion des régions réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Région du réseau * sont les concentrateurs réseau ou les dorsales utilisés dans la configuration de contrôle d’admission des appels, de E9-1-1 et de contournement de média.
ms.openlocfilehash: c08232e455edb4388a052c2859b35e6c137b890a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817483"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Gestion des régions réseau dans Skype Entreprise Server

Les *régions réseau* sont les concentrateurs réseau ou les dorsales utilisés dans la configuration de contrôle d’admission des appels, de E9-1-1 et de contournement de média. Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau. Par exemple, si vous avez déjà créé des régions réseau pour une seule fonctionnalité vocale, vous n’avez pas besoin de créer de nouvelles régions réseau. d’autres fonctionnalités avancées de voix entreprise utiliseront les mêmes régions réseau. Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central. 

Suivez les procédures décrites dans cet article pour afficher des informations sur la région du réseau ou créer, modifier ou supprimer des régions réseau. 

## <a name="view-network-region-information"></a>Afficher les informations relatives à la région du réseau 


Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques. Chaque région du réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution. Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour afficher les régions du réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo. Utilisez cette rubrique pour afficher les régions réseau existantes. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>Pour afficher des informations sur une région de réseau avec le panneau de configuration Skype entreprise Server

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.

4.  Dans la page **zone** , cliquez sur la zone que vous voulez afficher.
  
    > [!NOTE]  
    > Vous ne pouvez afficher qu’une région à la fois.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de région du réseau à l’aide des cmdlets Windows PowerShell

Vous pouvez afficher les informations relatives à la région du réseau à l’aide de Windows PowerShell et de l’applet **de requête get-CsNetworkRegion** . Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

### <a name="to-view-network-region-information"></a>Pour afficher les informations relatives aux régions du réseau

  - Pour afficher des informations sur toutes les régions de votre réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :
    
        Get-CsNetworkRegion
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .


## <a name="create-or-modify-network-regions"></a>Créer ou modifier des régions réseau 

Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques. Chaque région du réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution. Le panneau de configuration Skype entreprise Server vous permet de configurer des régions du réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo. Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer une région réseau. Utilisez cette rubrique pour créer et modifier des régions réseau. 

### <a name="to-create-a-network-region"></a>Pour créer une zone réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.

4.  Dans la page **région** , cliquez sur **nouveau**.

5.  Dans la page **nouvelle région** , tapez une valeur dans le champ **nom** . Cette valeur doit être unique dans le cadre de votre déploiement Skype entreprise Server.

6.  Dans la liste déroulante **site central** , sélectionnez le site central pour cette région réseau.

7.  La case à cocher **activer le chemin audio alternatif** est activée par défaut. Ce champ détermine si les appels audio seront routés par le biais d’un autre chemin si la bande passante suffisante n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement sur Internet. Si l’un de vos appels sera appelé appels Internet, cette case doit être cochée, quels que soient les paramètres de bande passante.

8.  La case à cocher **activer le chemin vidéo alternatif** est activée par défaut. Ce champ détermine si les appels vidéo sont routés par le biais d’une autre trajectoire si la bande passante suffisante n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement sur Internet. Si l’un de vos appels sera appelé appels Internet, cette case doit être cochée, quels que soient les paramètres de bande passante.

9.  Facultatif Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région qui ne peut pas être exprimée à l’aide du nom seul.

10. Cliquez sur **Valider**.

La table **site associée** n’est pas utilisée pour créer une région réseau. Vous associez un site à une région lorsque vous créez ou modifiez le site. Pour plus d’informations, consultez [gestion du contrôle d’admission des appels pour les sites](managing-call-admission-control-for-sites.md).

### <a name="to-modify-a-network-region"></a>Pour modifier une zone réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.

4.  Dans la page **zone** , cliquez sur la zone que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier la région** , vous pouvez modifier les paramètres d’activation et de désactivation des chemins audio et vidéo, et modifier la description (pour plus de détails, reportez-vous à la section « créer une région réseau » plus haut dans cette rubrique.

7.  Cliquez sur **Valider**.

Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie à des fins de référence, afin que vous soyez attentif aux sites qui seront affectés lors de la modification des paramètres régionaux.


## <a name="delete-existing-network-regions"></a>Supprimer des régions réseau existantes 

Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques. Chaque région du réseau doit être associée à un site central. Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution. Le panneau de configuration Skype entreprise Server vous permet de configurer des régions du réseau. Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo. Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer une région réseau. Utilisez cette rubrique pour supprimer des régions réseau existantes. 

### <a name="to-delete-a-network-region"></a>Pour supprimer une zone réseau

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.

4.  Dans la page **zone** , cliquez sur la zone que vous voulez supprimer.
  
    > [!NOTE]  
    > Vous pouvez supprimer plusieurs régions à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs régions tout en maintenant la touche CTRL enfoncée. Vous pouvez sélectionner toutes les **régions dans le** menu **Edition** .

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.


    > [!WARNING]  
    > Une région réseau ne peut pas être supprimée si elle est associée à un site réseau. Si vous tentez de supprimer une région associée à un site, un message d’erreur s’affiche. Pour déterminer si une région est associée à des sites, sélectionnez la région, puis cliquez sur **afficher les détails** dans le menu **modifier** .


## <a name="see-also"></a>Voir aussi

[Gestion des itinéraires de région réseau](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  

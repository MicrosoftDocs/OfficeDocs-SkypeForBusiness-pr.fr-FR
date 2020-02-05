---
title: Création ou modification d’un itinéraire vocal dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Résumé : Découvrez comment créer ou modifier un itinéraire vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: 8732a07e835e6888efbc132da8dc99a0b4263f29
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767797"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Création ou modification d’un itinéraire vocal dans Skype entreprise
 
**Résumé :** Découvrez comment créer ou modifier un itinéraire vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Pour créer une gamme vocale à l’aide du panneau de configuration Skype entreprise Server

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Cliquez sur **Itinéraire**.
    
5. Cliquez sur **Nouveau** pour afficher la boîte de dialogue **Nouvel itinéraire des communications vocales**.
    
6. Dans **Nom**, tapez un nom descriptif pour l’itinéraire des communications vocales.
    
7. (Facultatif) Dans **Description**, tapez une description complémentaire du nouvel itinéraire des communications vocales.
    
8. Pour spécifier les modèles que cet itinéraire doit prendre en compte, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre** ou l’écrire manuellement.
    
   - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
    
   - **Chiffres de départ pour les nombres que vous voulez autoriser**: entrez les valeurs de préfixe que cet itinéraire doit accepter (y compris les touches de début si nécessaire). Par exemple, tapez + 425, puis cliquez sur **Ajouter**. Répétez cette procédure pour chaque valeur de préfixe que vous voulez inclure dans l’itinéraire.
    
   - **Exceptions**: Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillance le préfixe et cliquez sur **exceptions**. Tapez une ou plusieurs valeurs pour les modèles correspondants pour lesquels vous ne souhaitez *pas* que cet itinéraire puisse être pris en charge. Par exemple, pour exclure les nombres commençant par + 425237 de l’itinéraire, entrez la valeur + 425237 dans le champ **exceptions** , puis cliquez sur **OK**.
    
   - Pour définir manuellement le modèle de correspondance, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis entrez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur la façon d’écrire des expressions régulières, consultez la rubrique [expressions régulières .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché pour le destinataire. Si vous sélectionnez cette option, vous devez spécifier un **autre ID d’appelant** qui s’affichera sur l’écran d’identification de l’appelant du destinataire.
    
10. Pour associer une ou plusieurs jonctions à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
11. Pour associer une ou plusieurs utilisations du réseau téléphonique commuté (RTC) à l’itinéraire des communications vocales, cliquez sur **Sélectionner** et sélectionnez un enregistrement dans la liste des enregistrements d’utilisation RTC définis pour votre déploiement de Voix Entreprise.
    
    > [!NOTE]
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation RTC disponibles, voir [afficher les enregistrements d’utilisation RTC dans Skype entreprise](view-pstn-usage-records.md). > de créer ou de modifier des enregistrements d’utilisation RTC, consultez [la rubrique créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation RTC dans Skype entreprise](voice-policy-and-pstn-usage-records.md) .
  
12. Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]
    > Contrairement à une stratégie de voix, l’ordre dans lequel les enregistrements d’utilisation RTC sont répertoriés dans l’itinéraire des communications vocales n’a pas d’importance. Nous vous recommandons, toutefois, d’organiser la liste par fréquence d’utilisation. Par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype entreprise Server parcourt la liste à partir du haut vers le bas.) 
  
13. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test s’affichent sous le champ.
    
14. Cliquez sur **OK** pour enregistrer l’itinéraire des communications vocales.
    
    > [!IMPORTANT]
    > Quand vous créez un itinéraire des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la configuration modifiée. Pour plus d’informations, reportez-vous [à la rubrique publier les modifications en attente sur la configuration de l’acheminement vocal dans Skype entreprise](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Pour modifier un itinéraire des communications vocales

1. Ouvrez le panneau de configuration Skype entreprise Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Itinéraire**.
    
3. Dans la page **Itinéraire**, utilisez l’une des méthodes ci-dessous pour modifier un itinéraire des communications vocales :
    
   - Sélectionnez un nom d’itinéraire des communications vocales, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
   - Sélectionnez un nom d’itinéraire des communications vocales, cliquez sur **Modifier**, sur **Copier** et enfin sur **Coller**. Sélectionnez la copie de l’itinéraire des communications vocales créée à l’instant, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
4. Dans la page **Modifier l’itinéraire des communications vocales**, dans le champ **Nom**, tapez un nom descriptif pour l’itinéraire des communications vocales.
    
5. (Facultatif) Dans le champ **Description**, tapez une description supplémentaire du nouvel itinéraire des communications vocales.
    
6. Pour spécifier les modèles que cet itinéraire doit prendre en compte, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre** ou l’écrire manuellement.
    
   - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
    
   - **Chiffres de départ pour les nombres que vous voulez autoriser**: entrez les valeurs de préfixe que cet itinéraire doit accepter (y compris les touches de début si nécessaire). Par exemple, tapez + 425, puis cliquez sur **Ajouter**. Répétez cette procédure pour chaque valeur de préfixe que vous voulez inclure dans l’itinéraire.
    
   - **Exceptions**: Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillance le préfixe et cliquez sur **exceptions**. Tapez une ou plusieurs valeurs pour les modèles correspondants pour lesquels vous ne souhaitez *pas* que cet itinéraire puisse être pris en charge. Par exemple, pour exclure les nombres commençant par + 425237 de l’itinéraire, entrez la valeur + 425237 dans le champ **exceptions** , puis cliquez sur **OK**.
    
   - Pour définir manuellement le modèle de correspondance, cliquez sur **modifier** dans l’outil **générer un modèle pour faire correspondre** , puis tapez dans une expression régulière .NET Framework pour spécifier le modèle correspondant aux numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur la façon d’écrire des expressions régulières, consultez la rubrique [expressions régulières .NET Framework](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché au destinataire. Si vous sélectionnez cette option, vous devez spécifier un **autre ID d’appelant** qui s’affichera sur l’écran d’identification de l’appelant du destinataire.
    
8. Pour associer une ou plusieurs jonctions RTC à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
9. Pour associer une ou plusieurs utilisations RTC à l’itinéraire vocal, cliquez sur **Sélectionner** et sélectionnez un enregistrement dans la liste des enregistrements d’utilisation RTC définis pour votre déploiement voix entreprise.
    
    > [!NOTE]
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation RTC disponibles, voir [afficher les enregistrements d’utilisation RTC dans Skype entreprise](view-pstn-usage-records.md). > de créer ou de modifier des enregistrements d’utilisation RTC, consultez [la rubrique créer ou modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Skype entreprise](voice-policy-and-pstn-usage-records.md). 
  
10. Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]
    > Contrairement à une stratégie de voix dans laquelle l’ordre d’apparition des enregistrements d’utilisation RTC est important, l’ordre des enregistrements d’utilisation RTC dans un itinéraire des communications vocales n’est pas significatif. Il est toutefois recommandé d’organiser la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype entreprise Server parcourt la liste à partir du haut vers le bas.) 
  
11. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
12. Cliquez sur **OK**.
    
13. Dans la page **Itinéraire**, cliquez sur **Valider**, puis sur **Tout valider**. 
    
    > [!NOTE]
    > Chaque fois que vous créez ou modifiez un itinéraire des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.
  
## <a name="see-also"></a>Voir aussi

[Afficher les enregistrements d’utilisation RTC dans Skype entreprise](view-pstn-usage-records.md)
  
[Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise](voice-policy-and-pstn-usage-records.md)
  
[Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise](voice-route-config-changes.md)


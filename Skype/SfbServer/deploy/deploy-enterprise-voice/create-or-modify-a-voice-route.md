---
title: Création ou modification d’un itinéraire de communications vocales dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Résumé : Apprenez à créer ou modifier un itinéraire de voix dans Skype pour 2015 de serveur d’entreprise à l’aide de la Skype pour le panneau de configuration de Business Server.'
ms.openlocfilehash: 2adc4d2a1277f229c1fcfbf230a49d5e91855a97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business-2015"></a>Création ou modification d’un itinéraire de communications vocales dans Skype Entreprise 2015
 
**Résumé :** Découvrez comment créer ou modifier un itinéraire de voix dans Skype pour 2015 de serveur d’entreprise à l’aide de la Skype pour le panneau de configuration de Business Server.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Pour créer un itinéraire de voix à l’aide de la Skype pour le panneau de configuration de Business Server

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Cliquez sur **Itinéraire**.
    
5. Cliquez sur **Nouveau** pour afficher la boîte de dialogue **Nouvel itinéraire des communications vocales**.
    
6. Dans **Nom**, tapez un nom descriptif pour l’itinéraire des communications vocales.
    
7. (Facultatif) Dans **Description**, tapez une description complémentaire du nouvel itinéraire des communications vocales.
    
8. Pour spécifier les modèles que cet itinéraire doit prendre en compte, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre** ou l’écrire manuellement.
    
   - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
    
   - **Démarrage des chiffres pour les numéros que vous souhaitez autoriser**: entrez les valeurs de préfixe qui doit s’adapter à cet itinéraire (y compris l’interligne + si nécessaire). Par exemple, tapez +425, puis cliquez sur **Ajouter**. Répétez cette procédure pour chaque valeur de préfixe que vous souhaitez inclure dans la gamme.
    
   - **Exceptions**: Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, le préfixe de mettre en surbrillance et cliquez sur **Exceptions**. Tapez dans une ou plusieurs valeurs pour la mise en correspondance de modèles que vous effectuez cette route pour prendre en charge que vous souhaitez *n’est pas* . Par exemple, pour exclure les numéros commençant par +425237 de la gamme, permet d’entrer une valeur de + 425237 dans le champ des **Exceptions** , puis cliquez sur **OK**.
    
   - Pour définir manuellement le modèle de correspondance, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis entrez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur l’écriture d’expressions régulières, consultez [«.NET Framework Regular Expressions »](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
9. Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché pour le destinataire. Si vous sélectionnez cette option, vous devez spécifier un **ID d’appelant de remplacement** qui apparaîtra sur les appelant du destinataire affichage de l’identifiant.
    
10. Pour associer une ou plusieurs jonctions à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
11. Pour associer une ou plusieurs utilisations du réseau téléphonique commuté (RTC) à l’itinéraire des communications vocales, cliquez sur **Sélectionner** et sélectionnez un enregistrement dans la liste des enregistrements d’utilisation RTC définis pour votre déploiement de Voix Entreprise.
    
    > [!NOTE]
    > Pour afficher les propriétés de chacun des enregistrements de l’utilisation de TLS disponibles, voir [enregistrements d’utilisation de vue RTPC dans Skype pour entreprise 2015](view-pstn-usage-records.md). > Pour créer ou modifier des enregistrements d’utilisation PSTN, consultez [créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](voice-policy-and-pstn-usage-records.md)
  
12. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement et cliquez sur la flèche vers le bas.
    
    > [!NOTE]
    > Contrairement à une stratégie de voix, l’ordre dans lequel les enregistrements d’utilisation RTC sont répertoriés dans l’itinéraire des communications vocales n’a pas d’importance. Nous vous recommandons, toutefois, d’organiser la liste par fréquence d’utilisation. Par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype pour Business Server parcourt la liste à partir du haut vers le bas.) 
  
13. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test s’affichent sous le champ.
    
14. Cliquez sur **OK** pour enregistrer l’itinéraire des communications vocales.
    
    > [!IMPORTANT]
    > Quand vous créez un itinéraire des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la configuration modifiée. Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md). 
  
### <a name="to-modify-a-voice-route"></a>Pour modifier un itinéraire des communications vocales

1. Ouvrez Skype pour le panneau de configuration de Business Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Itinéraire**.
    
3. Dans la page **Itinéraire**, utilisez l’une des méthodes ci-dessous pour modifier un itinéraire des communications vocales :
    
   - Sélectionnez un nom d’itinéraire des communications vocales, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
   - Sélectionnez un nom d’itinéraire des communications vocales, cliquez sur **Modifier**, sur **Copier** et enfin sur **Coller**. Sélectionnez la copie de l’itinéraire des communications vocales créée à l’instant, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
4. Dans la page **Modifier l’itinéraire des communications vocales**, dans le champ **Nom**, tapez un nom descriptif pour l’itinéraire des communications vocales.
    
5. (Facultatif) Dans le champ **Description**, tapez une description supplémentaire du nouvel itinéraire des communications vocales.
    
6. Pour spécifier les modèles que cet itinéraire doit prendre en compte, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre** ou l’écrire manuellement.
    
   - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
    
   - **Démarrage des chiffres pour les numéros que vous souhaitez autoriser**: entrez les valeurs de préfixe qui doit s’adapter à cet itinéraire (y compris l’interligne + si nécessaire). Par exemple, tapez +425 et puis cliquez sur **Ajouter**. Répétez cette procédure pour chaque valeur de préfixe que vous souhaitez inclure dans la gamme.
    
   - **Exceptions**: Si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, le préfixe de mettre en surbrillance et cliquez sur **Exceptions**. Tapez dans une ou plusieurs valeurs pour la mise en correspondance de modèles que vous effectuez cette route pour prendre en charge que vous souhaitez *n’est pas* . Par exemple, pour exclure les numéros commençant par +425237 de la gamme, permet d’entrer une valeur de + 425237 dans le champ des **Exceptions** , puis cliquez sur **OK**.
    
   - Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil de **génération d’un modèle à faire correspondre** et tapez dans une expression régulière du.NET Framework pour spécifier le modèle de correspondance pour les numéros de téléphone de destination à laquelle l’itinéraire est appliqué. Pour plus d’informations sur l’écriture d’expressions régulières, consultez [«.NET Framework Regular Expressions »](https://go.microsoft.com/fwlink/p/?linkId=140927). 
    
7. Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché au destinataire. Si vous sélectionnez cette option, vous devez spécifier un **ID d’appelant de remplacement** qui apparaîtra sur les appelant du destinataire affichage de l’identifiant.
    
8. Pour associer une ou plusieurs jonctions RTC à l’itinéraire des communications vocales, cliquez sur **Ajouter**, puis sélectionnez une jonction dans la liste.
    
9. Pour associer une ou plusieurs utilisations de RTPC à l’itinéraire de la voix, cliquez sur **Sélectionner** et choisissez un enregistrement dans la liste des enregistrements d’utilisation de TLS qui ont été définis pour votre déploiement de Voix Entreprise.
    
    > [!NOTE]
    > Pour afficher les propriétés de chacun des enregistrements de l’utilisation de TLS disponibles, voir [enregistrements d’utilisation de vue RTPC dans Skype pour entreprise 2015](view-pstn-usage-records.md). > Pour créer ou modifier des enregistrements d’utilisation PSTN, consultez [créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](voice-policy-and-pstn-usage-records.md). 
  
10. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement et cliquez sur la flèche vers le bas.
    
    > [!NOTE]
    > Contrairement à une stratégie de voix dans laquelle l’ordre d’apparition des enregistrements d’utilisation RTC est important, l’ordre des enregistrements d’utilisation RTC dans un itinéraire des communications vocales n’est pas significatif. Il est toutefois recommandé d’organiser la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype pour Business Server parcourt la liste à partir du haut vers le bas.) 
  
11. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
12. Cliquez sur **OK**.
    
13. Dans la page **Itinéraire**, cliquez sur **Valider**, puis sur **Tout valider**. 
    
    > [!NOTE]
    > Chaque fois que vous créez ou modifiez un itinéraire des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md) dans la documentation d’opérations.
  
## <a name="see-also"></a>Voir aussi

#### 

[Afficher les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](view-pstn-usage-records.md)
  
[Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation de TLS dans Skype pour entreprise 2015](voice-policy-and-pstn-usage-records.md)
  
[Publier des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md)


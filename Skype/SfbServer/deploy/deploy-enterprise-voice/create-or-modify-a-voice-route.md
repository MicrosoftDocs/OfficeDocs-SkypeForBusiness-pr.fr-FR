---
title: Créer ou modifier un itinéraire de voix dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 'Résumé : Découvrez comment créer ou modifier un itinéraire de voix dans Skype Entreprise Server à l’aide du Panneau de Skype Entreprise Server de conférence.'
ms.openlocfilehash: ee7f4a0f5d09a36fd1d8e5bcd88a15cd01cc6657
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755767"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Créer ou modifier un itinéraire de voix dans Skype Entreprise
 
**Résumé :** Découvrez comment créer ou modifier un itinéraire des Skype Entreprise Server à l’aide du Panneau de Skype Entreprise Server de conférence.
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>Pour créer un itinéraire de voix à l’aide du Skype Entreprise Server de contrôle

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Cliquez sur **Itinéraire**.
    
5. Cliquez sur **Nouveau** pour afficher la boîte de dialogue **Nouvel itinéraire de communications vocales**.
    
6. In **Name**, type a descriptive name for the voice route.
    
7. (Facultatif) Dans **Description,** tapez des informations descriptives supplémentaires pour l’itinéraire des voix.
    
8. Pour spécifier les modèles que cet itinéraire doit  prendre en charge, vous pouvez utiliser le modèle Créer un modèle pour faire correspondre l’outil pour générer une expression régulière ou écrire l’expression régulière manuellement.
    
   - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
    
   - **Chiffres de début pour les nombres** que vous souhaitez autoriser : entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le + de début si nécessaire). Par exemple, tapez +425, puis cliquez sur **Ajouter.** Répétez cette étape pour chaque valeur de préfixe que vous souhaitez inclure dans l’itinéraire.
    
   - **Exceptions**: si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillez le préfixe et cliquez sur **Exceptions.** Tapez une ou plusieurs valeurs pour  les modèles correspondants que vous ne souhaitez pas que cet itinéraire s’adaptera. Par exemple, pour exclure des nombres commençant par +425237 de l’itinéraire, entrez la valeur +425237 dans le champ **Exceptions,** puis cliquez sur **OK**.
    
   - Pour définir le modèle de correspondance manuellement, cliquez sur **Modifier** dans l’outil **Créer un modèle à suivre**, puis saisissez une expression régulière .NET Framework afin de spécifier le modèle de correspondance pour les numéros de téléphone de destination auxquels l’itinéraire est appliqué. Pour plus d’informations sur l’écriture d’expressions régulières, voir [« .NET Framework Expressions régulières](/dotnet/standard/base-types/regular-expressions)». 
    
9. Sélectionnez l’option **Supprimer l’ID de l’appelant** si vous ne souhaitez pas que l’ID du téléphone à l’origine de l’appel sortant soit affiché au destinataire. Si vous sélectionnez cette option, vous devez spécifier un **autre ID** d’appelant qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.
    
10. Pour associer une ou plusieurs liaisons  à l’itinéraire des messages vocaux, cliquez sur Ajouter, puis sélectionnez une trunk dans la liste.
    
11. Pour associer une ou plusieurs utilisations du réseau téléphonique commuté  (PSTN) à l’itinéraire des communications vocales, cliquez sur Sélectionner et choisir un enregistrement dans la liste des enregistrements d’utilisation PSTN qui ont été définis pour votre déploiement Voix Entreprise.
    
    > [!NOTE]
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation PSTN disponibles, voir Afficher les enregistrements d’utilisation [PSTN dans Skype Entreprise](view-pstn-usage-records.md). > pour créer ou modifier des enregistrements d’utilisation PSTN, voir Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation [PSTN dans Skype Entreprise](voice-policy-and-pstn-usage-records.md)
  
12. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, mettez en surbrillez le nom de l’enregistrement et cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]
    > Contrairement à une stratégie de voix où l’ordre dans lequel les enregistrements d’utilisation PSTN sont répertoriés est important, l’ordre dans lequel les enregistrements d’utilisation PSTN sont répertoriés dans l’itinéraire de voix n’est pas significatif. Toutefois, nous vous recommandons d’organiser la liste par fréquence d’utilisation. Par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype Entreprise Server parcourt la liste du haut vers le bas.) 
  
13. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
14. Cliquez sur **OK** pour enregistrer l’itinéraire de communications vocales.
    
    > [!IMPORTANT]
    > Chaque fois que vous créez un itinéraire de voix, vous devez exécuter la commande **Valider tout** pour publier la modification de configuration. Pour plus d’informations, voir Publier les modifications en attente de la configuration du [routage](voice-route-config-changes.md)des Skype Entreprise . 
  
### <a name="to-modify-a-voice-route"></a>Pour modifier un itinéraire de communications vocales

1. Ouvrez Skype Entreprise Server panneau de contrôle.
    
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Itinéraire**.
    
3. Dans la page **Itinéraire**, utilisez l’une des méthodes suivantes pour modifier un itinéraire de communications vocales :
    
   - Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
   - Sélectionnez un nom d’itinéraire de communications vocales, cliquez sur **Modifier**, puis sur **Copier** et enfin sur **Coller**. Sélectionnez la copie de l’itinéraire de communications vocales créée à l’instant, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
4. Dans la page **Modifier l’itinéraire de communications vocales**, dans le champ **Nom**, tapez un nom descriptif pour l’itinéraire de communications vocales.
    
5. (Facultatif) Dans le champ **Description**, tapez une description supplémentaire du nouvel itinéraire de communications vocales.
    
6. Pour spécifier les modèles que cet itinéraire doit prendre en charge, vous pouvez générer une expression régulière à l’aide de l’outil **Créer un modèle à suivre**, ou l’écrire manuellement.
    
   - Pour utiliser l’outil **Créer un modèle à suivre** afin de générer une expression régulière, entrez les valeurs comme suit. Vous pouvez spécifier deux types de correspondance de modèles :
    
   - **Chiffres de début des numéros que vous souhaitez autoriser** : Entrez les valeurs de préfixe que cet itinéraire doit prendre en charge (y compris le + à gauche si nécessaire). Tapez par exemple +425, puis cliquez sur **Ajouter**. Renouvelez cette procédure pour chaque valeur de préfixe à inclure dans l’itinéraire.
    
   - **Exceptions**: si vous souhaitez spécifier une ou plusieurs exceptions pour une valeur de préfixe, mettez en surbrillez le préfixe et cliquez sur **Exceptions.** Tapez une ou plusieurs valeurs pour  les modèles correspondants que vous ne souhaitez pas que cet itinéraire s’adaptera. Par exemple, pour exclure des nombres commençant par +425237 de l’itinéraire, entrez la valeur +425237 dans le champ **Exceptions,** puis cliquez sur **OK**.
    
   - Pour définir manuellement le  modèle de  correspondance, cliquez sur Modifier dans le modèle Créer un modèle pour correspondre à l’outil, puis tapez une expression régulière .NET Framework pour spécifier le modèle de correspondance pour les numéros de téléphone de destination auquel l’itinéraire est appliqué. Pour plus d’informations sur l’écriture d’expressions régulières, voir [« .NET Framework Expressions régulières](/dotnet/standard/base-types/regular-expressions)». 
    
7. Sélectionnez **Supprimer l’ID** de l’appelant si vous ne souhaitez pas que l’ID du téléphone qui fait l’appel sortant s’affiche pour le destinataire de l’appel. Si vous sélectionnez cette option, vous devez spécifier un **autre ID** d’appelant qui apparaîtra sur l’affichage de l’ID d’appelant du destinataire.
    
8. Pour associer une ou plusieurs liaisons PSTN (réseau téléphonique commuté) à l’itinéraire des communications vocales, cliquez sur **Ajouter,** puis sélectionnez une trunk dans la liste.
    
9. Pour associer une ou plusieurs utilisations PSTN  à l’itinéraire des services vocaux, cliquez sur Sélectionner et choisissez un enregistrement dans la liste des enregistrements d’utilisation PSTN qui ont été définis pour votre déploiement Voix Entreprise réseau.
    
    > [!NOTE]
    > Pour afficher les propriétés de chacun des enregistrements d’utilisation PSTN disponibles, voir Afficher les enregistrements d’utilisation [PSTN dans Skype Entreprise](view-pstn-usage-records.md). > pour créer ou modifier des enregistrements d’utilisation PSTN, voir Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation [PSTN dans Skype Entreprise](voice-policy-and-pstn-usage-records.md). 
  
10. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, mettez en surbrillez le nom de l’enregistrement et cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!NOTE]
    > Contrairement à une stratégie de voix dans laquelle l’ordre dans lequel les enregistrements d’utilisation PSTN sont répertoriés est important, l’ordre des enregistrements d’utilisation PSTN dans un itinéraire de voix n’est pas significatif. Il est toutefois recommandé d’organiser la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Skype Entreprise Server parcourt la liste du haut vers le bas.) 
  
11. (Facultatif) Tapez une valeur dans le champ **Entrez un numéro traduit à tester** et cliquez sur **OK**. Les résultats du test sont affichés sous le champ.
    
12. Cliquez sur **OK**.
    
13. Dans la page **Itinéraire**, cliquez sur **Valider**, puis sur **Valider tout**. 
    
    > [!NOTE]
    > Chaque fois que vous créez ou  modifiez un itinéraire de voix, vous devez exécuter la commande Valider tout pour publier la modification de configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.
  
## <a name="see-also"></a>Voir aussi

[Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise](view-pstn-usage-records.md)
  
[Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise](voice-policy-and-pstn-usage-records.md)
  
[Publier les modifications en attente de la configuration du routage des Skype Entreprise](voice-route-config-changes.md)
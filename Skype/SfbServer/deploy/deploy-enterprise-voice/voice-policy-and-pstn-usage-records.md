---
title: Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Résumé : Créez ou modifiez des stratégies de voix et configurez les enregistrements d’utilisation PSTN à l’aide Skype Entreprise Server panneau de configuration.'
ms.openlocfilehash: 988ce046e3ef5dbbf9020deeb79665b7fda3f9b2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386282"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise

**Résumé :** Créez ou modifiez des stratégies de voix et configurez les enregistrements d’utilisation PSTN à l’aide Skype Entreprise Server panneau de configuration.

> [!NOTE]
> Chaque stratégie de voix doit avoir au moins un enregistrement d’utilisation du réseau téléphonique commuté (PSTN) associé. Pour afficher la liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise et afficher leurs propriétés, voir Afficher les enregistrements d’utilisation [PSTN dans Skype Entreprise](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Pour créer une stratégie de voix

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de la voix**.

3. Dans la page **Stratégie de la voix**, cliquez sur **Nouveau** puis sélectionnez l’étendue de la nouvelle stratégie :

   - La **stratégie de site** s’applique à l’ensemble d’un site, à l’exception des utilisateurs ou groupes attribués à une stratégie d’utilisateur. Si vous sélectionnez l’étendue Site pour une stratégie, choisissez le site dans la boîte de dialogue **Sélectionner un site**. Si une stratégie de voix a déjà été créée pour un site, le site n’apparaît pas dans la boîte de dialogue **Sélectionner un site**.

   - Une **stratégie d’utilisateur** peut être appliquée à des utilisateurs ou à des groupes spécifiés.

4. Si l’étendue de la stratégie de voix est Utilisateur, entrez un nom descriptif de la stratégie dans le champ **Nom**.

    > [!NOTE]
    > Si l’étendue de la stratégie de voix est Site, le champ **Nom** de la boîte de dialogue **Nouvelle stratégie de voix** est prérempli avec le nom du site et ne peut pas être modifié.

5. (Optionnel) Entrez une description supplémentaire de la stratégie de voix.

6. Activez ou désactivez les cases à cocher suivantes pour activer ou désactiver chacune des **fonctionnalités d’appel** pour cette stratégie de voix :

   -  L’évitement de messagerie vocale empêche l’itinéraire immédiat des appels vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, hors batterie ou hors de portée.

     > [!NOTE]
     > Cette fonctionnalité est uniquement configurable via Skype Entreprise Server Management Shell

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Skype Entreprise Server offre un éventail beaucoup plus large d’options de configuration pour le transport d’appel. Par exemple, si une organisation ne souhaite pas autoriser le transfert des appels entrants à l’extérieur vers le réseau téléphonique commuté (PSTN), un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.

   - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Skype Entreprise Server, un délégué peut configurer la sonnerie simultanée qui permet aux appels entrants à son responsable de sonner toutes les cibles de sonnerie simultanée du délégué. Le délégué peut ainsi répondre avec une plus grande souplesse aux appels destinés au responsable. Activée par défaut.

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.

   - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre depuis un autre téléphone ou client. Désactivée par défaut.

   - **Sonnerie simultanée** permet aux appels entrants de sonner sur des téléphones supplémentaires (par exemple, un téléphone mobile) ou d’autres périphériques de système d’extrémité. Skype Entreprise Server offre un éventail beaucoup plus large d’options de configuration pour la sonnerie simultanée. Activée par défaut.

   - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.

   - Le réacheminer **PSTN** permet aux appels effectués par des utilisateurs affectés à cette stratégie à d’autres utilisateurs d’entreprise d’être réacheminés sur le réseau téléphonique privé (PSTN) si le réseau wan est saturé ou indisponible. Activée par défaut.

   - Le **remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.

     > [!NOTE]
     > La stratégie sera uniquement remplacée pour les appels entrants vers l’utilisateur et non pour les appels sortants qui sont passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est précisément enregistrée. Ce paramètre doit être utilisé avec modération et doit être réservé à la prise de décision appropriée en matière de contrôle d’admission des appels.

   - **Le** suivi des appels malveillants permet aux utilisateurs de signaler des appels malveillants (tels que des menaces) à l’aide de l’interface utilisateur du client, qui à son tour signale les appels dans les enregistrements des détails des appels (CDR). Désactivé par défaut.

   - **Busy options** active ou désactive Busy Options pour la stratégie de voix spécifiée. Busy Options permet aux appels entrants d’être acheminés vers la messagerie vocale ou rejetés avec une signal d’occupé lorsque l’utilisateur cible de l’appel est au téléphone. Busy Options est une nouvelle stratégie de voix introduite dans la mise à jour cumulative de juillet 2016. La vérification de ce paramètre active Busy Options et la désactivation de ce paramètre désactive Busy Options. Pour plus d’informations, voir [Plan for Busy Options for Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype Entreprise Server](install-and-configure-busy-options.md).

7. Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour choisir un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de voix, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation RSTN nomméRedmond pour les employés à temps plein situés à Redmond et un autre appeléRedmondTemps pour les employés temporaires.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié.

     c. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

   - Pour choisir un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

   - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

8. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, mettez en surbrillez le nom de l’enregistrement et cliquez sur la flèche vers le haut ou vers le bas.

    > [!IMPORTANT]
    > L’ordre dans lequel les enregistrements d’utilisation apparaissent dans la stratégie de voix est essentiel. Skype Entreprise Server parcourt la liste du haut vers le bas. Nous vous conseillons d’organiser la liste par fréquence d’utilisation ; par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée dans cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour utiliser les mêmes enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Routage avec les utilisations PSTN d’appel** dans le menu déroulant.

   - Pour autoriser le forwarding d’appel et la sonnerie simultanée aux utilisateurs Skype Entreprise internes uniquement, sélectionnez **l’option** Router vers les utilisateurs Skype Entreprise internes uniquement dans le menu déroulant. Les appels ne seront pas transférés vers des numéros PSTN externes.

   - Pour spécifier des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Acheminer à l’aide d’utilisations PSTN personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner des enregistrements d’utilisation PSTN existants ou créer des enregistrements d’utilisation PSTN spécifiquement pour le transfert d’appels et la sonnerie simultanée.

   - Pour choisir un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements que vous voulez associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de transfert d’appel et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de transfert d’appel et de sonnerie simultanée, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié.

     c. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

   - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

   - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

10. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro traduit à tester**.

11. Cliquez sur **OK**.

12. Dans la page **Stratégie de la voix**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > À chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

13. (Facultatif) La boîte d’écoute de messagerie vocale détecte qu’un appel a été immédiatement répondu par la messagerie vocale du téléphone mobile de l’utilisateur et déconnecte l’appel vers la messagerie vocale du téléphone mobile. Cela permet à l’appel de continuer à sonner sur les autres points de terminaison de l’utilisateur, ce qui permet à l’utilisateur de répondre à l’appel. Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, voir [Configure voice mail escape in Skype Entreprise](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Pour modifier une stratégie de voix

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de la voix**.

3. Dans la page **Stratégie de la voix**, double-cliquez sur le nom d’une stratégie de voix.

    > [!NOTE]
    > L’étendue et le nom ont été définis lors de la création de la stratégie de voix. Ils ne peuvent pas être modifiés.

4. (Facultatif) Dans **Modifier la stratégie de voix**, entrez d’autres informations décrivant la stratégie de voix.

5. Activez ou désactivez les cases à cocher suivantes, afin d’activer ou de désactiver chacune des **Fonctionnalités d’appel** :

   -  L’évitement de messagerie vocale empêche l’itinéraire immédiat des appels vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, hors batterie ou hors de portée.

     > [!NOTE]
     > Cette fonctionnalité est uniquement configurable via Skype Entreprise Server Management Shell

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Skype Entreprise Server offre un éventail beaucoup plus large d’options de configuration pour le transport d’appel. Par exemple, si une organisation ne souhaite pas autoriser le transfert des appels entrants à l’extérieur vers le réseau téléphonique commuté (PSTN), un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.

   - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Skype Entreprise Server, un délégué peut configurer la sonnerie simultanée qui permet aux appels entrants à son responsable de sonner toutes les cibles de sonnerie simultanée du délégué. Le délégué peut ainsi répondre avec une plus grande souplesse aux appels destinés au responsable. Activée par défaut.

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.

   - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre depuis un autre téléphone ou client. Désactivée par défaut.

   - **Sonnerie simultanée** permet aux appels entrants de sonner sur des téléphones supplémentaires (par exemple, un téléphone mobile) ou d’autres périphériques de système d’extrémité. Skype Entreprise Server offre un éventail beaucoup plus large d’options de configuration pour la sonnerie simultanée. Activée par défaut.

   - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.

   - Le réacheminer **PSTN** permet aux appels effectués par des utilisateurs affectés à cette stratégie à d’autres utilisateurs d’entreprise d’être réacheminés sur le réseau téléphonique privé (PSTN) si le réseau wan est saturé ou indisponible. Activée par défaut.

   - **Le remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie cac pour un utilisateur particulier. Désactivée par défaut.

     > [!NOTE]
     > La stratégie est uniquement remplacée pour les appels entrants vers l’utilisateur et non pour les appels sortants qui sont passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est précisément enregistrée. Ce paramètre doit être utilisé avec modération.

   - **Le suivi des** appels malveillants permet aux utilisateurs de signaler des appels malveillants (tels que des menaces) à l’aide de l’interface utilisateur du client, qui signale à son tour les appels dans les CDR. Désactivée par défaut.

6. Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour choisir un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de voix, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation RSTN nomméRedmond pour les employés à temps plein situés à Redmond et un autre enregistrement nomméRedmondTemps pour les employés temporaires.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié.

     c. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

   - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

   - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

7. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, mettez en surbrillez le nom de l’enregistrement et cliquez sur la flèche vers le haut ou vers le bas.

    > [!NOTE]
    > L’ordre dans lequel les enregistrements d’utilisation apparaissent dans la stratégie de voix est essentiel. Skype Entreprise Server parcourt la liste du haut vers le bas. Nous vous conseillons d’organiser la liste par fréquence d’utilisation ; par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée dans cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour utiliser les mêmes enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Routage avec les utilisations PSTN d’appel** dans le menu déroulant.

   - Pour autoriser le forwarding d’appel et la sonnerie simultanée à des utilisateurs Skype Entreprise internes uniquement, sélectionnez Router vers les utilisateurs Skype Entreprise **internes** uniquement dans le menu déroulant. Les appels ne seront pas transférés à des numéros PSTN externes.

   - Pour spécifier des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Routage avec des utilisations PSTN personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner les enregistrements d’utilisation PSTN existants ou créer de nouveaux enregistrements d’utilisation PSTN spécifiquement pour le transfert d’appel et la sonnerie simultanée.

   - Pour choisir un ou plusieurs enregistrements dans une liste d’enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de transfert d’appel et de sonnerie simultanée, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de transfert d’appel et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de transfert d’appel et de sonnerie simultanée, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié.

     c. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

   - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :

     - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

     - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, voir [Create or modify a voice route in Skype Entreprise](create-or-modify-a-voice-route.md).

     - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).

     c. Cliquez sur **OK**.

9. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro traduit à tester**.

10. Cliquez sur **OK**.

11. Dans la page **Stratégie de la voix**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

12. (Facultatif) La boîte d’écoute de messagerie vocale détecte qu’un appel a été immédiatement répondu par la messagerie vocale du téléphone mobile de l’utilisateur et déconnecte l’appel vers la messagerie vocale du téléphone mobile. Cela permet à l’appel de continuer à sonner sur les autres points de terminaison de l’utilisateur, ce qui permet à l’utilisateur de répondre à l’appel. Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, voir [Configure voice mail escape in Skype Entreprise](configure-voice-mail-escape.md).

## <a name="see-also"></a>Voir aussi

[Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise](view-pstn-usage-records.md)

[Créer ou modifier un itinéraire de voix dans Skype Entreprise](create-or-modify-a-voice-route.md)

[Publier les modifications en attente de la configuration du routage des Skype Entreprise](voice-route-config-changes.md)

[Configurer l’échappatoire de messagerie vocale dans Skype Entreprise](configure-voice-mail-escape.md)
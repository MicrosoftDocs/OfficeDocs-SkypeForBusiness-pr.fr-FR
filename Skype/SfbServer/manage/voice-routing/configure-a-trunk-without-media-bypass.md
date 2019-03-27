---
title: Configurer une jonction sans contournement de média dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Pour configurer une jonction avec l’option de déviation du trafic multimédia activée, procédez comme suit. '
ms.openlocfilehash: 623de0439e6c6297808e54eb2ae050aa95f6533d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881931"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Configurer une jonction sans contournement de média dans Skype pour Business Server

Pour configurer une jonction sur laquelle la déviation du trafic multimédia est désactivée, procédez comme suit. Si vous souhaitez configurer une jonction avec contournement de média activé, voir [configurer une jonction avec support de contournement dans Skype pour Business Server](configure-a-trunk-with-media-bypass.md).

Une configuration de jonction, comme indiqué dans la suite de cette rubrique, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

**Pour configurer une jonction sans déviation du trafic multimédia**

1. Ouvrez Skype pour serveur Busines le panneau de configuration.
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
4. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :
        - **Jonction de site**: choisissez le site pour cette configuration de jonction dans **Sélectionner un Site**, puis cliquez sur **OK**. Notez que si une configuration de tronçon a déjà été créée pour un site, le site n’apparaît pas dans la zone **Sélectionner un Site**. Cette configuration de jonction sera appliquée à toutes les jonctions dans le site.
        - **Jonction de pool**: choisissez le nom du segment auquel s’applique cette configuration de jonction dans **Sélectionner un Service** , cliquez sur **OK**. Cette jonction peut être la jonction racine, ou les jonctions supplémentaires définies dans le Générateur de topologie. Notez que si une configuration de tronçon a déjà été créée pour une jonction spécifique, la jonction n’apparaît pas dans la zone **Sélectionner un Service**.
    > [!Note] 
    > Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée. Le champ **Nom** est prérempli et comporte le nom du site ou du service associé à la configuration de jonction. Ce nom ne peut pas être modifié. 

5. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX.
    - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge par le fournisseur de services ou le fabricant, il ne peut pas être utilisé.
6. Assurez-vous que la case à cocher **Activer la déviation du trafic multimédia** est désactivée.
7. Activez la case à cocher **multimédia centralisée traitement** si un média connu est le point de terminaison (par exemple, un public commuté (PSTN) passerelle de réseau où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.
8. Si l’homologue de jonction prend en charge la réception de demandes SIP REFER à partir du serveur de médiation, activez la case à cocher **permettre l’envoi de faire référence à la passerelle** .
9. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations PSTN associées à cette configuration de jonction seront appliquées pour tous les appels entrants par le biais de la jonction qui n’est pas provenant d’un Skype pour le point de terminaison Business Server. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :
    - Pour sélectionner un ou plusieurs enregistrements d’une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    - Pour supprimer un enregistrement d’utilisation RTC de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette configuration de jonction, procédez comme suit :
        1. Cliquez sur **Nouveau**.
        2. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            > [!Note] 
            > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**. 

        3. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
            - Pour sélectionner un ou plusieurs itinéraires à partir de la liste de tous les itinéraires disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        4. Cliquez sur **OK**.
    - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette configuration de jonction, procédez comme suit :
        1. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.
        2. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
            - Pour sélectionner un ou plusieurs itinéraires à partir de la liste de tous les itinéraires disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        3. Cliquez sur **OK**.

    > [!Important] 
    > Il est important d’associer des enregistrements d’utilisation PSTN en fonction de l’homologue du serveur de médiation qui est associé à la jonction en cours de configuration. Si l’homologue du serveur de médiation est une passerelle PSTN ou un contrôleur de Session en périphérie (SBC), il est fortement recommandé que la configuration de jonction n’est pas associée à un enregistrement d’utilisation PSTN qui achemine vers une destination PSTN ou tous les autres systèmes en aval connecté via Skype pour un serveur d’entreprise. 

10. Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation RTC, puis cliquez sur la flèche vers le haut ou vers le bas.
    > [!Important] 
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Skype pour Business Server parcourt la liste du haut vers le bas. 

11. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière un convertisseur d’adresses réseau (NAT) ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.
12. **Activer l’historique du transfert d’appel** doit être sélectionné pour permettre l’envoi des informations d’historique des appels à l’homologue de passerelle du serveur de médiation.
13. **Activer les données de transfert P-Asserted-Identity** doit être sélectionné pour activer les informations de PAI à transférer entre le côté serveur de médiation et le côté passerelle (et vice versa), lorsque présenter.
14. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. Redirection vers une autre jonction se produit si cette notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.
15. (Facultatif) Associer et **configurer des règles de traduction de numéros appel** pour la jonction. Ces règles de traduction s’appliquent au numéro appelant pour les appels sortants.
    - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [définition des règles de traduction dans Skype pour Business Server](defining-translation-rules.md).
    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, voir [définition des règles de traduction dans Skype pour Business Server](defining-translation-rules.md).
    - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, voir [définition des règles de traduction dans Skype pour Business Server](defining-translation-rules.md).
    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

    > [!Warning]
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 

16. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.
    - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans Sélectionner des règles de traduction, cliquez sur les règles que vous souhaitez associer à la jonction, puis cliquez sur **OK**.
    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [définition des règles de traduction dans Skype pour Business Server](defining-translation-rules.md).
    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, voir [définition des règles de traduction dans Skype pour Business Server](defining-translation-rules.md).
    - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, voir [définition des règles de traduction dans Skype pour Business Server](defining-translation-rules.md).
    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

    > [!Caution] 
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 

17. Vérifiez que les règles de conversion s’affichent dans l’ordre adéquat. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!Important] 
    > Skype pour Business Server parcourt la liste des règles de traduction à partir du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si une règle de conversion s’applique à tout numéro à 11 chiffres et qu’une autre s’applique à tout numéro à 11 chiffres commençant par +1425, vérifiez que la règle qui s’applique à tout numéro à 11 chiffres s’affiche après la règle la plus restrictive. 

18. Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.
19. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**. 

    > [!Note]
    > Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, voir publication en attente apportées à la configuration de routage voix dans Lync Server 2013 dans la documentation des opérations. 

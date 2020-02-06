---
title: Configuration d’une Trunk with Media bypass dans Skype entreprise Server
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
description: 'Pour configurer une jonction avec l’option de déviation du trafic multimédia activée, procédez comme suit. '
ms.openlocfilehash: 3628c0ea38c0692b313ee37ca7b836c159a5a2dd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817034"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configuration d’une Trunk with Media bypass dans Skype entreprise Server

Pour configurer une jonction avec l’option de déviation du trafic multimédia activée, procédez comme suit. Pour configurer un Trunk avec contournement de média désactivé, voir [configurer un Trunk sans dérivation multimédia dans Skype entreprise Server](configure-a-trunk-without-media-bypass.md). La dérivation de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. En règle générale, un pool de serveurs de médiation est déployé sur un site central et contrôle les passerelles dans les sites de succursales. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels PSTN (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Les itinéraires des appels sortants de Skype entreprise Server et les stratégies voix entreprise doivent être correctement configurés de sorte que les appels RTC de clients sur un site de succursale soient routés vers la passerelle appropriée.

Nous vous conseillons vivement d’activer la déviation du trafic multimédia. Cependant, avant de l’activer sur une jonction SIP (Session Initiation Protocol), assurez-vous que votre fournisseur de jonctions SIP compétent prend en charge cette option et qu’il peut satisfaire aux exigences d’activation du scénario. Plus spécifiquement, le fournisseur doit disposer des adresses IP des serveurs sur le réseau interne de votre organisation. Si le fournisseur ne peut pas prendre en charge ce scénario, la contournement de média ne fonctionnera pas. Pour plus d’informations, reportez-vous à la rubrique [planification de la dérivation de médias dans Skype entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> La dérivation multimédia n’interagit pas avec chaque passerelle réseau téléphonique commuté (RTC), PBX IP et contrôleur de bordure de session (SBC). Microsoft a testé plusieurs passerelles RTC et contrôleurs SBC en collaboration avec des partenaires agréés et a effectué différents tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et versions qui sont répertoriés dans la page [de l’infrastructure de téléphonie de Skype entreprise Server](../../../SfbPartnerCertification/certification/infra-gateways.md) . 


Une configuration de jonction, décrite ci-dessous, regroupe un ensemble de paramètres appliqués aux jonctions auxquelles cette configuration de jonction est affectée. Une configuration de jonction spécifique peut posséder une étendue globale (applicable à toutes les jonctions qui ne disposent pas d’une configuration de pool ou de site plus spécifique) ou une étendue Site ou Pool. La configuration de jonction au niveau du pool sert à appliquer une configuration de jonction spécifique à une jonction unique.

**Pour configurer une jonction avec la déviation du trafic multimédia**

1. Ouvrez le panneau de configuration Skype pour entreprise Server.
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
3. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :
        - **Jonction de site** : sélectionnez le site de la configuration de jonction dans **Sélectionner un site**, puis cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour un site, ce site ne s’affiche pas dans **Sélectionner un site**. Cette configuration de jonction sera appliquée à toutes les jonctions du site.
        - **Trunk de pool**: sélectionnez le nom du Trunk auquel cette configuration de Trunk s’applique. Ce Trunk peut être le Trunk racine ou d’éventuelles liaisons supplémentaires définies dans le générateur de topologie. Dans **Sélectionner un service**, cliquez sur **OK**. Notez que si une configuration de Trunk a déjà été créée pour une ligne particulière, le Trunk n’apparaît pas dans **Sélectionner un service**.
    
    > [!NOTE]
    > Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée. Le champ **Nom** est prérempli et comporte le nom du site ou du service associé à la configuration de jonction. Ce nom ne peut pas être modifié. 

5. Spécifiez une valeur dans **Nombre maximal de boîtes de dialogue anticipées prises en charge**. Il s’agit du nombre maximal de réponses dirigées qu’une passerelle RTC, IP-PBX ou qu’un contrôleur SBC (Session Border Controller) d’un fournisseur de services de téléphonie et Internet (ITSP) peut recevoir à une INVITATION envoyée au serveur de médiation. La valeur par défaut est 20.

    > [!NOTE] 
    > Avant de modifier cette valeur, consultez votre fournisseur de services ou le fabricant de matériel pour plus d’informations sur les capacités de votre système. 

6. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX.
    - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge par le fournisseur de services ou le fabricant, il ne peut pas être utilisé.
7. Activez la case à cocher **Activer la déviation du trafic multimédia** si vous souhaitez que le trafic multimédia contourne le serveur de médiation pour être traité par l’homologue de jonction.

    > [!IMPORTANT]
    > Pour que la déviation du trafic multimédia fonctionne correctement, la passerelle RTC, un IP-PBX ou un contrôleur SBC ITSP doit prendre en charge certaines fonctionnalités. Pour plus d’informations, reportez-vous à la rubrique [planification de la dérivation de médias dans Skype entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Activez la case à cocher **Traitement multimédia centralisé** s’il existe un point de terminaison multimédia connu (par exemple, une passerelle RTC où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.
9. Si l’homologue de Trunk prend en charge la réception des demandes de renvoi SIP du serveur de médiation, activez la case à cocher **activer l’envoi** . 

    > [!NOTE] 
    > Si vous désactivez cette option alors que l’option **Activer la déviation du trafic multimédia** est sélectionnée, des paramètres supplémentaires sont requis. Si l’homologue de jonction ne prend pas en charge la réception des requêtes SIP (Session Initiation Protocol) REFER du serveur de médiation et si la déviation du trafic multimédia est activée, vous devez également exécuter l’applet de commande **Set-CsTrunkConfiguration** pour désactiver le RTCP pour les appels en cours ou en attente afin de prendre en charge les conditions appropriées à la déviation du trafic multimédia. En guise d’alternative, vous pouvez sélectionner **Activer la référence avec un contrôle d’appel tiers** si vous souhaitez que les appels transférés soient soumis à la déviation du trafic multimédia et que la passerelle ne prend pas en charge les demandes SIP (Session Initiation Protocol) REFER. 

10. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations RTC associées à cette configuration de Trunk s’appliquent à tous les appels entrants par le biais du Trunk qui n’est pas issu d’un point de terminaison de Skype entreprise Server. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :
    - Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    - Pour supprimer un enregistrement d’utilisation RTC de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette configuration de jonction, procédez comme suit :
        1. Cliquez sur **Nouveau**.
        2. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            > [!NOTE] 
            > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**. 
        3. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        4. Cliquez sur **OK**.
    - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette configuration de jonction, procédez comme suit :
        1. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.
        2. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        3. Cliquez sur **OK**.

    > [!Important]
    > Il est important d’associer les enregistrements d’utilisation RTC en fonction de l’homologue du serveur de médiation associé au Trunk en cours de configuration. S’il s’agit d’une passerelle PSTN ou d’un contrôleur de bordure de session (SBC), il est vivement recommandé que la configuration de Trunk ne soit pas associée à un enregistrement d’utilisation RTC qui achemine vers une destination PSTN ou tout autre système en aval connecté par le biais de Skype. pour Business Server. 

11. Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation RTC, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!Important]
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Skype entreprise Server parcourt la liste de haut en bas. 

12. L’option **Activer l’accrochage RTP** doit être sélectionnée pour activer la déviation du trafic multimédia pour les clients situés derrière un pare-feu ou un convertisseur d’adresses réseau (NAT) et un contrôleur SBC qui prend en charge l’accrochage.
13. L’option **activer l’historique des appels en aval** doit être sélectionnée pour permettre l’envoi des informations de l’historique des appels à l’homologue de la passerelle du serveur de médiation.
14. **Activez le transfert des données d’identité p-assertion** qui doivent être sélectionnées pour permettre aux informations de l’appelant d’appeler p-assertion (PAI) d’être transmises entre le côté du serveur de médiation et le côté passerelle (et vice versa), le cas échéant.
15. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. Le reroutage vers un autre Trunk se produit si la notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.
16. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de traduction s’appliquent au numéro d’appel pour les appels sortants.
    - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, reportez-vous à la rubrique [définition des règles de traduction dans Skype entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Skype entreprise Server](defining-translation-rules.md).
    - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Skype entreprise Server](defining-translation-rules.md).
    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    > [!Warning]
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 

17. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.
    - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, reportez-vous à la rubrique [définition des règles de traduction dans Skype entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Skype entreprise Server](defining-translation-rules.md).
    - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Skype entreprise Server](defining-translation-rules.md).
    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

    > [!Warning] 
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 

18. Vérifiez que les règles de conversion s’affichent dans l’ordre adéquat. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.

    >[!Important] 
    > Skype entreprise Server parcourt la liste des règles de traduction du haut vers le bas et utilise la première règle correspondant au numéro numéroté. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si une règle de conversion s’applique à tout numéro à 11 chiffres et qu’une autre s’applique à tout numéro à 11 chiffres commençant par +1425, vérifiez que la règle qui s’applique à tout numéro à 11 chiffres s’affiche *après* la règle la plus restrictive. 

19. Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.
20. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**. 

    > [!Note]
    > Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la section publier les modifications en attente dans la configuration de routage](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx) (VOUS AVEZ BESOIN D’UN NOUVEAU LIEN ?)

Après avoir configuré le Trunk, continuez à configurer le contournement multimédia en choisissant entre les options de contournement de médias globales, comme décrit dans la rubrique déploiement d’une [dérivation multimédia dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).


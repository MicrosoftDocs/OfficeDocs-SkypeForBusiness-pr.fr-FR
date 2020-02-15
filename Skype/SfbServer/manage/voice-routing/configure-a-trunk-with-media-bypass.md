---
title: Configuration d’une jonction avec la déviation du trafic multimédia dans Skype entreprise Server
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
description: 'Procédez comme suit pour configurer une jonction avec la déviation du trafic multimédia activée. '
ms.openlocfilehash: 293c39884c1ef6c8e82521b3fd248ae6bbc18d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009547"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configuration d’une jonction avec la déviation du trafic multimédia dans Skype entreprise Server

Procédez comme suit pour configurer une jonction avec la déviation du trafic multimédia activée. Pour configurer une jonction avec la déviation du trafic multimédia désactivée, consultez [la rubrique Configure a trunk without Media Bypass in Skype for Business Server](configure-a-trunk-without-media-bypass.md). Le contournement de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. Un pool de serveurs de médiation est généralement déployé sur un site central et contrôle des passerelles sur des sites de succursale. L’activation du contournement de média permet aux médias de passer des appels PSTN (Public Switched Telephone Network) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Les itinéraires d’appels sortants de Skype entreprise Server et les stratégies de voix entreprise doivent être correctement configurés de sorte que les appels PSTN des clients d’un site de succursale soient acheminés vers la passerelle appropriée.

Nous vous recommandons vivement d’activer la déviation du trafic multimédia. Toutefois, avant d’activer la déviation du trafic multimédia sur une jonction SIP, vérifiez que votre fournisseur de jonction SIP qualifié prend en charge la déviation du trafic multimédia et est capable de s’accommoder de la configuration requise pour activer le scénario. Plus précisément, le fournisseur doit disposer des adresses IP des serveurs sur le réseau interne de votre organisation. Si le fournisseur ne prend pas en charge ce scénario, la déviation du trafic multimédia échouera. Pour plus d’informations, reportez-vous à la rubrique [plan for Media Bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle PSTN (réseau téléphonique commuté), PBX IP et contrôleur SBC (session Border Controller). Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et versions répertoriés sur la page [infrastructure de téléphonie pour Skype entreprise Server](../../../SfbPartnerCertification/certification/infra-gateways.md) . 


Une configuration de jonction, comme décrit ci-dessous, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

**Pour configurer une jonction avec la déviation du trafic multimédia**

1. Ouvrez le panneau de configuration de Skype outil Server.
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
3. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    - Cliquez sur **Nouvelle**, puis sélectionnez l’étendue de la nouvelle configuration de jonction :
        - **Jonction de sites**: choisissez le site pour cette configuration de jonction dans **Sélectionner un site**, puis cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour un site, le site ne s’affiche pas dans **Sélectionner un site**. Cette configuration de jonction sera appliquée à toutes les jonctions du site.
        - **Jonction de pool**: choisissez le nom de la jonction à laquelle cette configuration de jonction s’applique. Cette jonction peut être la jonction racine ou toute autre jonction définie dans le générateur de topologie. Dans **Sélectionner un service**, cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour une jonction spécifique, la jonction ne s’affiche pas dans **Sélectionner un service**.
    
    > [!NOTE]
    > Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable. Le champ **Nom** est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable. 

5. Spécifiez une valeur dans la **boîte de dialogue maximum Early pris en charge**. Il s’agit du nombre maximal de réponses avec branches qu’une passerelle PSTN (réseau téléphonique commuté), un système IP-PBX ou un contrôleur SBC (session Border Controller) téléphonie Internet peut recevoir à une invitation qui est envoyée au serveur de médiation. La valeur par défaut est 20.

    > [!NOTE] 
    > Avant de modifier cette valeur, consultez votre fournisseur de services ou le fabricant de votre équipement pour obtenir plus d’informations sur les fonctionnalités de votre système. 

6. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (private branch exchange).
    - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge pas le fournisseur de services ou le fabricant, il ne peut pas être utilisé.
7. Activez la case à cocher **activer le contournement de média** si vous souhaitez que les médias contournent le serveur de médiation pour le traitement par l’homologue de jonction.

    > [!IMPORTANT]
    > Pour que la déviation du trafic multimédia fonctionne correctement, la passerelle PSTN, le système IP-PBX ou le contrôleur de session téléphonie Internet doit prendre en charge certaines fonctionnalités. Pour plus d’informations, reportez-vous à la rubrique [plan for Media Bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Activez la case à cocher **traitement multimédia centralisé** s’il existe un point de terminaison de média connu (par exemple, une passerelle RTC où l’arrêt du média a la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.
9. Si l’homologue de jonction prend en charge la réception des demandes SIP REFER à partir du serveur de médiation, activez la case à cocher **activer l’envoi en tant que passerelle** . 

    > [!NOTE] 
    > Si vous désactivez cette option alors que l’option Activer la déviation du trafic **multimédia** est sélectionnée, des paramètres supplémentaires sont requis. Si l’homologue de jonction ne prend pas en charge la réception des demandes SIP REFER à partir du serveur de médiation et que la déviation du trafic multimédia est activée, vous devez également exécuter l’applet de commande **Set-applet cstrunkconfiguration** pour désactiver le protocole RTCP pour les appels actifs et conservés afin de prendre en charge les conditions appropriées pour la déviation du trafic multimédia. Vous pouvez également sélectionner **Enable voir Using tiers-Call Control** si vous voulez que les appels transférés soient détournées de médias et que la passerelle ne prenne pas en charge les demandes SIP refer. 

10. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation PSTN à la configuration de cette jonction. Les utilisations RTC associées à cette configuration de jonction seront appliquées à tous les appels entrants par le biais de la jonction qui n’est pas provenant d’un point de terminaison Skype entreprise Server. Pour gérer les enregistrements d’utilisation PSTN associés à une configuration de jonction, utilisez l’une des méthodes suivantes :
    - Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    - Pour supprimer un enregistrement d’utilisation PSTN de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette configuration de jonction, procédez comme suit :
        1. Cliquez sur **Nouveau**.
        2. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            > [!NOTE] 
            > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié. 
        3. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        4. Cliquez sur **OK**.
    - Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette configuration de jonction, procédez comme suit :
        1. Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.
        2. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        3. Cliquez sur **OK**.

    > [!Important]
    > Il est important d’associer les enregistrements d’utilisation PSTN en fonction de l’homologue de serveur de médiation associé à la jonction en cours de configuration. Si l’homologue du serveur de médiation est une passerelle RTC ou un contrôleur de frontière de session (SBC), il est vivement recommandé que la configuration de jonction ne soit pas associée à un enregistrement d’utilisation PSTN qui achemine vers une destination PSTN ou tout autre système en aval connecté via Skype pour Business Server. 

11. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!Important]
    > L’ordre des enregistrements d’utilisation PSTN dans la liste de la configuration de jonction a son importance. Skype entreprise Server parcourt la liste de haut en bas. 

12. **Activer le verrouillage RTP** doit être sélectionné pour activer le support de contournement pour les clients derrière une traduction d’adresses réseau (NAT) ou un pare-feu et un contrôleur SBC prenant en charge le verrouillage.
13. **Activer l’historique du transfert d’appel** doit être sélectionné pour permettre l’envoi des informations d’historique d’appel à l’homologue de passerelle du serveur de médiation.
14. **Activer les données de transfert p-asserted-Identity** doit être sélectionné pour permettre aux informations d’origine de l’appel de p-asserted-Identity (PAI) d’être transférées entre le côté serveur de médiation et la passerelle (et vice versa), le cas échéant.
15. **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionné pour permettre un basculement rapide. La passerelle associée à cette jonction peut informer dans les 10 secondes du traitement de l’appel sortant. La redirection vers une autre jonction se produira si cette notification n’est pas reçue par le serveur de médiation. Sur des réseaux avec une latence qui peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.
16. (Facultatif) Associez et configurez les **règles de traduction du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro d’appel pour les appels sortants.
    - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Skype entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [Defining translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à la rubrique [Defining translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.
    > [!Warning]
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit. 

17. (Facultatif) Associez et configurez les **règles de traduction de numéro appelé** pour la jonction. Les règles de traduction s’appliquent au numéro appelé dans un appel sortant.
    - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Skype entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [Defining translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à la rubrique [Defining translation Rules in Skype for Business Server](defining-translation-rules.md).
    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

    > [!Warning] 
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit. 

18. Assurez-vous que les règles de traduction de la jonction sont organisées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.

    >[!Important] 
    > Skype entreprise Server parcourt la liste de règles de traduction du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de traduction, assurez-vous que les règles les plus restrictives apparaissent avant les règles les moins restrictives. Par exemple, si une règle de traduction s’applique à tout numéro à 11 chiffres et une autre s’applique à tout numéro à 11 chiffres commençant par +1425, assurez-vous que la règle qui s’applique à tout numéro à 11 chiffres apparaît *après* la règle la plus restrictive. 

19. Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.
20. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 

    > [!Note]
    > À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, consultez [la rubrique publier des modifications en attente dans la configuration du routage des communications vocales](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). (VOUS AVEZ BESOIN D’UN NOUVEAU LIEN ?)

Une fois que vous avez configuré la jonction, poursuivez la configuration du contournement de média en choisissant entre les options de contournement de média global, comme décrit dans [Deploy Media Bypass in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).


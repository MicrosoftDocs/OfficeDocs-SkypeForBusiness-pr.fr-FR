---
title: Configurer le profil utilisateur
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 842a5ade3e0484d0b084f48ac75a2b13984706e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Configurer le profil utilisateur

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2018-10-11_

Les outils inclus dans le package d’outils de contrainte et de performances de Lync Server 2013 vous permettent de créer et de configurer des comptes d’utilisateurs test que vous pouvez utiliser pour exécuter des simulations de charge. Utilisez l’outil de création d’utilisateurs Lync Server 2013 pour créer les utilisateurs. (Pour plus d’informations, consultez la rubrique [créer des utilisateurs et des contacts](create-users-and-contacts.md).) Une fois les utilisateurs créés, configurez les profils utilisateur à l’aide de l’outil de configuration de chargement Lync Server 2013.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Exécution de l’outil de configuration de chargement Lync Server 2013

Pour configurer les profils utilisateur, exécutez l’outil de configuration de chargement Lync Server 2013 (UserProfileGenerator. exe) et renseignez chacun des onglets. UserProfileGenerator. exe génère un répertoire pour chacun des ordinateurs clients dont vous avez besoin pour exécuter la simulation. Chaque annuaire client est également fourni avec un script pour démarrer toutes les instances de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool. exe).

<div>


> [!IMPORTANT]  
> Les valeurs propres à l’utilisateur spécifiées dans UserProfileGenerator doivent correspondre aux valeurs spécifiées dans l’outil de création d’utilisateurs Lync Server 2013 (UserProvisioningTool) pour le pool.



</div>

Renseignez les champs de chaque onglet de l’outil de configuration de chargement de Lync Server 2013, comme décrit dans les sections suivantes.

<div>

## <a name="common-configuration"></a>Configuration commune

L’onglet **configuration commune** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante. Renseignez les champs de l’onglet **configuration courante** , comme décrit dans les étapes suivantes.

![Onglet Configuration commune.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Onglet Configuration commune.")

1.  Dans **nombre d’ordinateurs disponibles**, tapez ou cliquez sur le nombre d’ordinateurs que vous souhaitez utiliser pour exécuter LyncPerfTool. exe. Nous vous recommandons de disposer d’un ordinateur pour chaque 4 500 utilisateurs que vous simulerez. Ce nombre peut varier si vous réduisez le niveau de charge ou si vous utilisez uniquement un sous-ensemble des fonctionnalités disponibles. (Les niveaux de charge sont définis sous l’onglet **scénarios généraux** .)

2.  Dans **préfixe pour les noms d’utilisateur**, tapez le préfixe du nom d’utilisateur des utilisateurs. Pour se connecter, l’URI (Uniform Resource Identifier) est : index de\[démarrage de l’utilisateur UserPrefix... (Nombre d’utilisateurs-1) \]@User domaine.

3.  Dans **mot de passe pour tous les utilisateurs**, entrez le mot de passe utilisé pour créer les utilisateurs. Si vous laissez ce champ vide, le nom d’utilisateur sera utilisé comme mot de passe.

4.  Dans **index de démarrage**de l’utilisateur, cliquez sur ou tapez l’index du premier utilisateur à configurer. Vous pouvez configurer des plages différentes pour différents types ou niveaux de charge, mais vous devez exécuter UserProfileGenerator. exe une fois par plage que vous souhaitez configurer.

5.  Dans **nombre d’utilisateurs**, cliquez sur ou tapez le nombre total d’utilisateurs que vous allez configurer.

6.  Dans **domaine**de l’utilisateur, tapez le domaine utilisé pour l’URI SIP. Il est utilisé pour construire l’URI SIP de chaque utilisateur afin de se connecter au serveur frontal Lync Server 2013 ou au serveur Standard Edition. Il peut être différent du domaine de compte.

7.  Dans **domaine de compte**, tapez connexion au domaine des services de domaine Active Directory.

8.  Entrez le nombre maximal de points de terminaison simultanés dans **se connecter par seconde (par instance)** pour lesquels l’outil doit se connecter à tous les points de terminaison/utilisateurs. Le taux recommandé est \<= 2 par seconde/standard SKU Fe.

9.  Dans le proxy d’accès ou le nom de **domaine complet du pool**, tapez le nom de domaine complet (FQDN) du serveur auquel vous souhaitez que les clients se connectent. Si les utilisateurs se connectent en externe, spécifiez le proxy d’accès. Si les utilisateurs sont internes, spécifiez le nom de domaine complet (FQDN) de leur pool ou serveur Standard Edition Server.

10. Dans **port**, cliquez ou tapez le port que les utilisateurs doivent utiliser pour SIP (la valeur par défaut est 5061).

Pour les paramètres de serveur réseau externe, spécifiez le **nom de domaine complet du pool ou du proxy d’accès** et le **port**. Ces paramètres ne sont utilisés que pour la simulation de charge de point de terminaison externe.

</div>

<div>

## <a name="general-scenarios"></a>Scénarios généraux

L’onglet **scénarios généraux** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.

Configurez les niveaux de charge et les paramètres pour chaque scénario général que vous souhaitez exécuter ou laissez-le désactivé.

![Onglet scénarios généraux.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Onglet scénarios généraux.")

1.  Dans la **messagerie instantanée**, qui inclut peer-to-peer et Conferencing, spécifiez la valeur appropriée pour le niveau de charge.
    
    <div>
    

    > [!NOTE]  
    > Les valeurs de niveau de charge pour tous les champs (à l’exception des services d’informations sur les emplacements) sont <STRONG>désactivées</STRONG>, <STRONG>faible</STRONG>, <STRONG>moyenne</STRONG>, <STRONG>haute</STRONG>et <STRONG>personnalisée</STRONG>. Lorsque la sélection est faible, moyenne, haute ou personnalisée, des configurations sont générées pour chaque modalité et client. La valeur élevée entraîne la génération du nombre maximal de charges prises en charge pour le serveur, moyenne correspond à 60% de la charge et la valeur faible correspond à 30% de la charge.

    
    </div>

2.  Dans l' **audioconférence**, qui est l’audioconférence uniquement, spécifiez la valeur appropriée pour le niveau de charge. Les appels P2P sont abordés dans la section scénarios vocaux plus loin dans cette rubrique. Pour activer MultiView, ouvrez l’onglet **avancé** pour cette modalité.

3.  Dans **partage d’application**, spécifiez la valeur appropriée pour le niveau de charge.

4.  Dans la **collaboration de données**, qui inclut la Conférence de données, spécifiez la valeur appropriée pour le niveau de charge.

5.  Dans **expansion**de la liste de distribution, spécifiez la valeur appropriée pour le niveau de charge. Vous devez également cliquer sur le bouton **avancé** , puis renseignez les champs avec les mêmes valeurs que celles configurées dans l’onglet **liste de distribution** de l’outil de création d’utilisateurs Lync Server (UserProvisioningTool. exe). Pour plus d’informations sur ces champs, voir [Create Users and contacts](create-users-and-contacts.md) .

6.  Dans la **requête Web du carnet d'** adresses, qui est le service de recherche de carnet d’adresses (et non le téléchargement du fichier de carnet d’adresses), spécifiez la valeur appropriée pour le niveau de charge. Pour activer les téléchargements de carnet d’adresses, cliquez sur le bouton **avancé** correspondant, puis définissez **EnableABSDownload** sur true.

7.  Dans **service Response Group**, spécifiez la valeur appropriée pour le niveau de charge. Vous devez également cliquer sur le bouton **avancé** correspondant, puis spécifier les URI des groupes Response Group que vous avez déjà créés lors de la mise en service des agents de service Response Group. Vous devez spécifier au moins un groupe Response Group. Utilisez des points-virgules pour séparer plusieurs groupes Response Group. Mettez à jour RGSUriSuffixStartIndex et RGSUriSuffixEndIndex avec les valeurs réelles.

8.  Dans **location Information Services**, sélectionnez la valeur appropriée pour le niveau de charge. Le niveau de charge pour les services d’informations d’emplacement doit être **activé** ou **désactivé**.

<div>


> [!NOTE]  
> Chacun des scénarios comprend un bouton <STRONG>avancé</STRONG> , ainsi qu’un ensemble de cases à cocher permettant d’activer des variantes des scénarios. Les moyens <STRONG>ad-hoc</STRONG> permettent de générer une simulation de conférences qui seront créées pendant l’heure. Le <STRONG>grand conf</STRONG> signifie que le scénario de grande conférence sera simulé. <STRONG>External</STRONG> signifie également simuler les utilisateurs externes.<BR>Ces boutons et cases à cocher permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et rendre la personnalisation possible. Pour chaque scénario sous l’onglet <STRONG>général scénarios</STRONG> (à l’exception des services d’informations sur l’emplacement), si la valeur de niveau de charge est <STRONG>personnalisée</STRONG>, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> . Le nom du champ diffère, selon le scénario, mais la description du champ indique « NOTE : ce numéro sera utilisé uniquement si Custom est sélectionné dans le menu déroulant. » En règle générale, les valeurs <STRONG>élevé</STRONG>, <STRONG>moyen</STRONG>et <STRONG>faible</STRONG> modifient les taux de conversation par modalité en fonction du modèle utilisateur qui est un équilibre de tous les scénarios. S’il est nécessaire de modifier le niveau de charge par modalité en raison d’une différence dans l’utilisation attendue, nous vous recommandons d’utiliser un taux de conversation <STRONG>personnalisé</STRONG> .<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>Scénarios vocaux

L’onglet **scénarios vocaux** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.

Utilisez l’onglet **scénarios vocaux** pour configurer tous les scénarios liés à la voix.

![Onglet scénarios vocaux.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Onglet scénarios vocaux.")

1.  Dans **VoIP**, cliquez sur le bouton **avancé** , puis fournissez des valeurs pour les champs **PhoneAreaCode** et **LocationProfile** (plan de numérotation). Vous devez également spécifier une valeur pour le **niveau de charge**. Si le niveau de charge pour les passerelles **VoIP** et **UC/PSTN** est activé, un réseau téléphonique commuté (PSTN) vers un fichier de configuration de communications unifiées (UC) sera toujours généré pour simuler les appels externes.

2.  Dans **passerelle cu/PSTN**, spécifiez une valeur pour le niveau de charge. Si vous sélectionnez un niveau de charge autre que **désactivé**, vous devez fournir une valeur pour le **Code de zone PSTN** en cliquant sur le bouton **Ajouter** sous serveur de médiation et RTC. Vérifiez que vous disposez d’un itinéraire configuré pour l’indicatif régional correspondant.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser le panneau de configuration Lync Server ou Lync Server Management Shell pour vérifier la configuration de l’itinéraire des communications vocales.

    
    </div>

3.  Dans le **service de surveillance de conférence**, spécifiez une valeur pour le niveau de charge. La sélection d’un niveau de charge (autre que **désactivé**) active le champ **numéro de téléphone** . Entrez le numéro de téléphone du standard automatique que vous souhaitez utiliser. De plus, cliquez sur le bouton **avancé** , puis spécifiez une valeur pour le champ **LocationProfile** .

4.  Dans **service de parcage d’appel**, spécifiez la valeur appropriée pour le **niveau de charge**.

5.  Dans **serveur de médiation et RTC**, pour chaque serveur de médiation que vous souhaitez utiliser, vous devez disposer d’un simulateur RTC distinct. Une fois que vous avez déterminé le client que vous allez utiliser en tant que simulateur, vous devez configurer votre serveur de médiation pour acheminer les appels vers cet ordinateur sur le port de simulateur RTC que vous avez configuré. Cliquez sur **Ajouter** pour configurer la valeur du serveur de médiation.

<div>


> [!NOTE]  
> Chacun des scénarios dispose d’un bouton <STRONG>avancé</STRONG> situé en regard. Ces boutons permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et d’activer la personnalisation. Pour chaque scénario sous l’onglet <STRONG>scénarios vocaux</STRONG> , si la valeur de <STRONG>niveau de charge</STRONG> est <STRONG>personnalisée</STRONG>, le taux de conversation sera calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> . Le nom du champ diffère, selon le scénario, mais la description du champ indique « NOTE : ce numéro sera utilisé uniquement si Custom est sélectionné dans le menu déroulant. »



</div>

</div>

<div>

## <a name="reach"></a>Jusqu'

La portée est une nouvelle expérience de Lync Server 2013 qui prend en charge les scénarios de conférence via le serveur UCWA (Unified Communications Web API) installé sur le serveur frontal. L’onglet **atteindre** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.

Utilisez l’onglet **atteindre** pour configurer tous les scénarios liés à la portée.

![Onglet atteindre](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Onglet atteindre")

1.  Cliquez sur le bouton **avancé** en regard de **paramètres de portée générale**. Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool directeur ou sur l’adresse IP virtuelle du pool frontal.

2.  Dans **partage d’application**, **collaboration de données**et **messagerie instantanée**, sélectionnez la valeur appropriée pour le **niveau de charge**.

<div>


> [!NOTE]  
> Chacun des scénarios dispose d’un bouton <STRONG>avancé</STRONG> situé en regard. Ces boutons permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et d’activer la personnalisation. Pour chacun des scénarios de portée, si le <STRONG>niveau de charge</STRONG> est <STRONG>Custom</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut



</div>

Utilisez l’onglet **mobilité** pour configurer tous les scénarios liés à la mobilité.

![Onglet mobilité.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Onglet mobilité.")

1.  Cliquez sur le bouton **avancé** en regard de **mobilité (UCWA)**. Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool directeur ou sur l’adresse IP virtuelle du pool frontal.

2.  Dans la **présence et l’audio\\de la messagerie instantanée P2P**, sélectionnez la valeur appropriée pour le **niveau de charge** pour activer la simulation de scénario de mobilité.

<div>


> [!NOTE]  
> Chacun des scénarios dispose d’un bouton <STRONG>avancé</STRONG> situé en regard. Ces boutons permettent d’accéder aux valeurs spécifiques à chaque scénario qui modifieront le comportement de l’outil de contrainte et performances de Lync Server 2013 (LyncPerfTool) et d’activer la personnalisation. Pour chacun des scénarios de portée, si le <STRONG>niveau de charge</STRONG> est <STRONG>Custom</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut.



</div>

</div>

<div>

## <a name="summary"></a>Résumé

L’onglet **Résumé** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.

![Onglet Résumé.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Onglet Résumé.")

L’onglet **Résumé** indique les utilisateurs à utiliser pour chacun des scénarios. Il est possible de configurer manuellement des plages de numéros d’utilisateur en activant la case à cocher **activer la génération personnalisée** de la plage d’utilisateurs, puis en double-cliquant sur le scénario dans le tableau qui contient la **plage d’utilisateurs** que vous souhaitez personnaliser. Check (RunClient. bat) ajoutez un retard de connexion au démarrage, afin d’inclure des retards dans les fichiers de commandes générés pour correspondre au taux de connexion. Ceci est utile pour empêcher la surcharge de serveur lors de la connexion d’un grand nombre d’utilisateurs. Cliquez sur **générer des fichiers**, puis sélectionnez le dossier où vous souhaitez générer la configuration. Une boîte de dialogue semblable à la figure suivante apparaît lorsque les fichiers ont été correctement créés.

![Accusé de réception de la création de fichiers.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Accusé de réception de la création de fichiers.")

</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer des utilisateurs et des contacts](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>

---
title: Configurer un profil utilisateur
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
ms.openlocfilehash: a2441fe97bb57ffdf0f6200f1201e192bfc6bf14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Configurer un profil utilisateur

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2018-10-11_

Les outils inclus dans le package d’outils de stress et de performance de Lync Server 2013 vous permettent de créer et de configurer des comptes d’utilisateurs test que vous pouvez utiliser pour effectuer des simulations de charge. Utilisez l’outil de création d’utilisateurs de Lync Server 2013 pour créer les utilisateurs. (Pour plus d’informations, consultez [créer des utilisateurs et des contacts](create-users-and-contacts.md).) Une fois les utilisateurs créés, configurez les profils utilisateur à l’aide de l’outil de configuration de chargement de Lync Server 2013.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Exécution de l’outil de configuration de chargement de Lync Server 2013

Pour configurer les profils utilisateur, exécutez l’outil de configuration de chargement de Lync Server 2013 (UserProfileGenerator. exe), puis remplissez chacun des onglets. UserProfileGenerator. exe génère un répertoire pour chaque ordinateur client dont vous avez besoin pour exécuter la simulation. Chaque répertoire client est également fourni avec un script permettant de démarrer toutes les instances de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool. exe).

<div>


> [!IMPORTANT]  
> Les valeurs spécifiques à l’utilisateur spécifiées dans UserProfileGenerator doivent correspondre aux valeurs spécifiées dans l’outil de création d’utilisateurs de Lync Server 2013 (UserProvisioningTool) pour le pool.



</div>

Renseignez les champs de chaque onglet de l’outil de configuration de chargement de Lync Server 2013, comme décrit dans les sections suivantes.

<div>

## <a name="common-configuration"></a>Configuration courante

L’onglet **configuration commune** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure ci-dessous. Remplissez les champs de l’onglet **configuration courante** , comme décrit dans les étapes suivantes.

![Onglet Configuration commune.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Onglet Configuration commune.")

1.  Dans **nombre d’ordinateurs disponibles**, tapez ou cliquez sur le nombre d’ordinateurs que vous voulez utiliser pour exécuter LyncPerfTool. exe. Nous vous recommandons d’avoir un ordinateur pour tous les utilisateurs de 4 500 que vous allez simuler. Ce nombre peut varier si vous réduisez le niveau de charge ou si vous utilisez uniquement un sous-ensemble des fonctionnalités disponibles. (Les niveaux de charge sont définis sous l’onglet **scénarios généraux** .)

2.  Dans **préfixe pour noms d’utilisateur**, tapez le préfixe correspondant au nom d’utilisateur des utilisateurs. Pour vous connecter, il s’agit de l’URI (Uniform Resource Identifier)\[: UserPrefix de début de l’utilisateur... (Nombre d’utilisateurs-1) \]@User domaine.

3.  Dans **mot de passe pour tous les utilisateurs**, entrez le mot de passe utilisé pour créer les utilisateurs. Si vous laissez ce champ vide, le nom d’utilisateur sera utilisé comme mot de passe.

4.  Dans **index de début**de l’utilisateur, cliquez ou tapez l’index du premier utilisateur à configurer. Vous pouvez configurer différentes plages pour différents types ou niveaux de charge, mais vous devez exécuter UserProfileGenerator. exe une seule fois par la plage que vous souhaitez configurer.

5.  Dans **nombre d’utilisateurs**, cliquez ou tapez le nombre total d’utilisateurs que vous allez configurer.

6.  Dans **domaine**de l’utilisateur, tapez le domaine utilisé pour l’URI SIP. Il est utilisé pour créer l’URI SIP de chaque utilisateur pour se connecter au serveur frontal Lync Server 2013 ou Standard Edition Server. Il peut être différent du domaine du compte.

7.  Dans **domaine de compte**, tapez la connexion au domaine AD FS (Active Directory Domain Services).

8.  Entrez le nombre maximal de points de terminaison concurrents en **se connectant par seconde (par instance)** pour lesquels vous voulez que l’outil se connecte à tous les points de terminaison/utilisateurs. Le taux recommandé est \<= 2 par seconde/standard PT.

9.  Dans **proxy d’accès ou nom de domaine complet du pool**, tapez le nom de domaine complet (FQDN) du serveur auquel vous souhaitez que les clients se connectent. Si les utilisateurs se connectent en externe, spécifiez le proxy d’accès. Si les utilisateurs sont internes, spécifiez le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition.

10. Dans **port**, cliquez ou tapez le port que les utilisateurs utiliseront pour SIP (la valeur par défaut est 5061).

Pour les paramètres de serveur de réseau externe, spécifiez le **nom de domaine complet du proxy ou du pool d’accès** et le **port**. Ces paramètres sont utilisés uniquement pour la simulation de charge de points de terminaison externes.

</div>

<div>

## <a name="general-scenarios"></a>Scénarios généraux

L’onglet **scénarios généraux** de l’outil de configuration de chargement de Lync Server 2013 est présenté dans la figure ci-dessous.

Configurez les niveaux de charge et les paramètres pour chacun des scénarios généraux que vous souhaitez exécuter, ou laissez-le désactivé.

![Onglet scénarios généraux.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Onglet scénarios généraux.")

1.  Dans la **messagerie instantanée**, qui inclut les services d’égal à égal et de conférence, spécifiez la valeur appropriée pour le niveau de charge.
    
    <div>
    

    > [!NOTE]  
    > Les valeurs de niveau de charge de tous les champs (à l’exception des services d’informations de lieu) sont <STRONG>désactivées</STRONG>, <STRONG>faible</STRONG>, <STRONG>moyenne</STRONG>, <STRONG>haute</STRONG>et <STRONG>personnalisée</STRONG>. Lorsque les valeurs faible, moyenne, haute ou personnalisée sont sélectionnées, des configurations sont générées pour chaque modalité et chaque client. Élevé entraîne la génération de la valeur maximale prise en charge pour le serveur, moyenne correspond à 60% du chargement et la valeur basse correspond à 30% du chargement.

    
    </div>

2.  Dans **audioconférence**, qui est le niveau de conférences audio uniquement, spécifiez la valeur appropriée pour le niveau de charge. Les appels d’égal à égal sont abordés dans la section scénarios vocaux, plus loin dans cette rubrique. Pour activer multivue, ouvrez l’onglet **avancé** pour cette modalité.

3.  Dans **partage d’application**, spécifiez la valeur appropriée pour le niveau de charge.

4.  Dans la **collaboration de données**, qui inclut les conférences de données, spécifiez la valeur appropriée pour le niveau de charge.

5.  Dans **extension**de la liste de distribution, spécifiez la valeur appropriée pour le niveau de charge. Vous devez également cliquer sur le bouton **avancé** , puis renseigner les champs avec les mêmes valeurs que celles configurées sous l’onglet **liste de distribution** de l’outil de création d’utilisateurs de Lync Server (UserProvisioningTool. exe). Pour plus d’informations sur ces champs, voir [créer des utilisateurs et des contacts](create-users-and-contacts.md) .

6.  Dans la **requête Web du carnet d'** adresses, qui est le service de recherche dans le carnet d’adresses (et non le téléchargement du fichier du carnet d’adresses), spécifiez la valeur appropriée pour le niveau de charge. Pour activer les téléchargements du carnet d’adresses, cliquez sur le bouton **avancé** correspondant, puis affectez à **EnableABSDownload** la valeur true.

7.  Dans **service Response Group**, spécifiez la valeur appropriée pour le niveau de charge. Vous devez également cliquer sur le bouton **avancé** correspondant, puis spécifier les URI des groupes de réponse que vous avez déjà créés lors de la mise en service des agents de groupe de réponse. Vous devez spécifier au moins un groupe de réponse. Utilisez des points-virgules pour séparer plusieurs groupes de réponse. Mettez à jour RGSUriSuffixStartIndex et RGSUriSuffixEndIndex sur les valeurs réelles.

8.  Dans **services d’information d’emplacement**, sélectionnez la valeur appropriée pour le niveau de charge. Le niveau de charge des services d’information d’emplacement doit être **activé** ou **désactivé**.

<div>


> [!NOTE]  
> Chacun des scénarios est associé à un bouton <STRONG>avancé</STRONG> qui s’affiche à côté de celui-ci, ainsi qu’un ensemble de cases à cocher permettant de définir des variations des scénarios. Moyens <STRONG>ad-hoc</STRONG> pour générer une simulation de conférences qui seront créées tout au long de l’heure. L’environnement de <STRONG>grande taille</STRONG> signifie que le scénario de conférence sera simulé. <STRONG>Externe</STRONG> signifie également simuler des utilisateurs externes.<BR>Ces boutons et cases à cocher autorisent l’accès à des valeurs propres à chaque scénario, qui modifient le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool) et permettent la personnalisation possible. Pour chaque scénario sous l’onglet <STRONG>scénarios généraux</STRONG> (à l’exception de services d’information d’emplacement), si la valeur de niveau de charge est <STRONG>personnalisé</STRONG>, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> . Le nom du champ est différent selon le scénario, mais la description du champ indique le message suivant : « Remarque : ce numéro sera utilisé uniquement si personnalisé est sélectionné dans le menu déroulant. » En règle générale, les valeurs <STRONG>élevé</STRONG>, <STRONG>moyen</STRONG>et <STRONG>faible</STRONG> modifient les taux de conversation par modalité en fonction du modèle utilisateur qui est un bilan de tous les scénarios. S’il est nécessaire de modifier le niveau de charge par modalité en raison d’une différence d’utilisation prévue, nous vous recommandons d’utiliser une fréquence de conversation <STRONG>personnalisée</STRONG> .<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>Scénarios vocaux

L’onglet **scénarios vocaux** de l’outil de configuration de chargement de Lync Server 2013 est présenté dans la figure ci-dessous.

Utilisez l’onglet **scénarios vocaux** pour configurer tous les scénarios liés à la voix.

![Onglet scénarios vocaux.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Onglet scénarios vocaux.")

1.  Dans **VoIP**, cliquez sur le bouton **avancé** , puis spécifiez des valeurs pour les champs **PhoneAreaCode** et **LocationProfile** (plan de numérotation). Vous devez également spécifier une valeur pour le **niveau de charge**. Si le niveau de **** charge des **passerelles VoIP et RTC/PSTN** est activé, un fichier de configuration de réseau téléphonique commuté (PSTN) vers des communications unifiées (UC) est toujours généré qui simule des appels externes.

2.  Dans **passerelle UC/PSTN**, spécifiez une valeur pour niveau de charge. Si vous sélectionnez un niveau de charge différent de **désactivé**, vous devez indiquer une valeur pour le **Code de zone RTC** en cliquant sur le bouton **Ajouter** sous serveur de médiation et RTC. Vérifiez que vous disposez d’un itinéraire configuré pour ce code de zone.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez utiliser le panneau de configuration de Lync Server ou Lync Server Management Shell pour vérifier la configuration des itinéraires vocaux.

    
    </div>

3.  Dans le **surveillant de conférences**, spécifiez une valeur pour le niveau de charge. Le choix d’un niveau de charge (différent de **désactivé**) permettra d’activer le champ **numéro de téléphone** . Entrez le numéro de téléphone du standard automatique que vous souhaitez utiliser. Cliquez sur le bouton **avancé** , puis spécifiez une valeur pour le champ **LocationProfile** .

4.  Dans **service de parc d’appels**, spécifiez la valeur appropriée pour le **niveau de charge**.

5.  Sur le **serveur de médiation et sur PSTN**, pour chaque serveur de médiation que vous souhaitez utiliser, vous devez disposer d’un simulateur PSTN distinct. Une fois que vous avez déterminé le client que vous allez utiliser comme simulateur, vous devez configurer votre serveur de médiation pour router les appels vers cet ordinateur sur le port de simulateur PSTN que vous avez configuré. Cliquez sur **Ajouter** pour configurer la valeur du serveur de médiation.

<div>


> [!NOTE]  
> Dans chacun des scénarios, un bouton <STRONG>avancé</STRONG> est placé en regard. Ces boutons autorisent l’accès à des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), et activez la personnalisation. Pour chaque scénario sous l’onglet <STRONG>scénarios vocaux</STRONG> , si la valeur de <STRONG>niveau de charge</STRONG> est <STRONG>personnalisée</STRONG>, le taux de conversation est calculé à l’aide du champ correspondant dans la boîte de dialogue <STRONG>avancé</STRONG> . Le nom du champ est différent selon le scénario, mais la description du champ indique le message suivant : « Remarque : ce numéro sera utilisé uniquement si personnalisé est sélectionné dans le menu déroulant. »



</div>

</div>

<div>

## <a name="reach"></a>Arrivez

La fonction joindre est une nouvelle interface de Lync Server 2013 qui prend en charge les scénarios de conférence via le serveur UCWA (Unified Communications Web API) installé sur le serveur frontal. L’onglet **joindre** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure suivante.

Utilisez l’onglet **joindre** pour configurer tous les scénarios liés à la portée.

![Onglet joindre](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Onglet joindre")

1.  Cliquez sur le bouton **avancé** en regard de **paramètres d’atteinte générale**. Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool de réalisateurs ou le VIP du pool frontal.

2.  Dans **partage d’application**, **collaboration de données**et **messagerie instantanée**, sélectionnez la valeur appropriée pour le **niveau de charge**.

<div>


> [!NOTE]  
> Dans chacun des scénarios, un bouton <STRONG>avancé</STRONG> est placé en regard. Ces boutons autorisent l’accès à des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), et activez la personnalisation. Pour chacun des scénarios d’atteinte, si le <STRONG>niveau de charge</STRONG> est <STRONG>personnalisé</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut



</div>

Utilisez l’onglet **mobilité** pour configurer tous les scénarios liés à la mobilité.

![Onglet mobilité.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Onglet mobilité.")

1.  Cliquez sur le bouton **avancé** en regard de **mobilité (UCWA)**. Définissez le champ **UcwaTargetServerUrl** sur l’adresse IP virtuelle du pool de réalisateurs ou le VIP du pool frontal.

2.  Sur le **son de présence et\\de messagerie instantanée P2P**, sélectionnez la valeur appropriée pour **niveau de charge** pour activer la simulation de scénarios de mobilité.

<div>


> [!NOTE]  
> Dans chacun des scénarios, un bouton <STRONG>avancé</STRONG> est placé en regard. Ces boutons autorisent l’accès à des valeurs propres à chaque scénario, qui changeront le comportement de l’outil de stress et de performance de Lync Server 2013 (LyncPerfTool), et activez la personnalisation. Pour chacun des scénarios d’atteinte, si le <STRONG>niveau de charge</STRONG> est <STRONG>personnalisé</STRONG>, la valeur spécifiée dans le champ <STRONG>ConversationsPerHour</STRONG> est utilisée à la place de la valeur par défaut.



</div>

</div>

<div>

## <a name="summary"></a>Résumé

L’onglet **Résumé** de l’outil de configuration de chargement de Lync Server 2013 est illustré dans la figure ci-dessous.

![Onglet Résumé.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Onglet Résumé.")

L’onglet **Résumé** indique quels utilisateurs utiliser pour chacun des scénarios. Il est possible de configurer manuellement la plage des numéros d’utilisateur en activant la case à cocher Activer la génération de plages d' **utilisateurs personnalisés** , puis en double-cliquant sur le scénario dans la table dont vous souhaitez **personnaliser la plage d’utilisateurs.** Regardez (RunClient. bat) ajoutez un délai de connexion au démarrage, afin d’inclure les retards dans les fichiers de commandes générés pour correspondre au taux de connexion. Cela peut s’avérer utile pour éviter une surcharge du serveur lors de la connexion d’un grand nombre d’utilisateurs. Cliquez sur **générer des fichiers**, puis sélectionnez le dossier dans lequel vous voulez générer la configuration. Une boîte de dialogue similaire à la figure suivante s’affichera lors de la création de vos fichiers.

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

---
title: 'Lync Server 2013 : Configuration des certificats pour l’interface Edge externe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Configuration des certificats pour l’interface Edge externe pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant certificat, assurez-vous que vous êtes connecté à l’aide d’un compte associé à un compte qui dispose des autorisations appropriées pour le type de modèle de certificat que vous utilisez. Par défaut, une demande de certificat du serveur Lync utilise le modèle de certificat de serveur Web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat à l’aide de ce modèle, vérifiez que le groupe a été affecté aux autorisations d’inscription requises pour utiliser ce modèle.



</div>

Chaque serveur Edge nécessite un certificat public sur l’interface entre le réseau de périmètre et Internet, et le nom de l’autre sujet du certificat doit contenir les noms externes du service Edge d’accès et du service Edge de conférence Web entièrement noms de domaine qualifiés (FQDN).

Pour plus d’informations sur ce problème et sur les autres exigences relatives aux certificats, voir [exigences relatives aux certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Pour obtenir une liste des autorités de certification publiques qui fournissent des certificats qui répondent à des exigences spécifiques pour les certificats de communications unifiées et qui ont été associés à Microsoft pour s’assurer qu’ils fonctionnent avec l’Assistant certificat de Lync Server 2013, voir Article 929395 de la base de connaissances Microsoft, «partenaires de certification de communications unifiées pour Exchange Server et [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)pour Communications Server» au.

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Configuration de certificats sur les interfaces externes

Pour configurer un certificat sur l’interface latérale externe sur un site, suivez les procédures décrites dans cette section pour effectuer les opérations suivantes:

  - Créez une demande de certificat pour l’interface externe du serveur Edge.

  - Envoyez la demande à votre autorité de certification publique.

  - Importez le certificat pour l’interface externe de chaque serveur Edge.

  - Attribuez le certificat pour l’interface externe de chaque serveur Edge.

  - Si votre déploiement inclut plusieurs serveurs Edge, exportez le certificat en même temps que sa clé privée, puis copiez-le sur l’autre serveur Edge. Ensuite, pour chaque serveur Edge, importez-le et attribuez-le comme décrit précédemment. Répétez cette procédure pour chaque serveur Edge.

Vous pouvez demander des certificats publics directement auprès d’une autorité de certification (CA) publique (par exemple, à partir du site Web d’une autorité de certification publique). Les procédures décrites dans cette section utilisent l’Assistant Certificat pour la plupart des tâches de certificat. Si vous avez choisi de demander un certificat directement auprès d’une autorité de certification publique, vous devez modifier chaque procédure en fonction de la demande, du transport et de l’importation du certificat, ainsi que de l’importation de la chaîne de certificats.

Lorsque vous demandez un certificat auprès d’une autorité de certification externe, les informations d’identification fournies doivent disposer de droits de demande de certificat de cette autorité de certification. Chaque autorité de certification dispose d’une stratégie de sécurité qui définit les informations d’identification (c’est-à-dire, les noms d’utilisateurs et de groupes spécifiques) autorisées à demander, émettre, gérer ou lire des certificats.

Si vous décidez d’utiliser la console MMC (Microsoft Management Console) pour importer des certificats, vous devez les importer dans le magasin de certificats de l’ordinateur. Si vous les importez dans le magasin de certificats d’utilisateur ou de service, le certificat ne sera pas disponible pour attribution dans l’Assistant certificat de Lync Server 2013.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>Pour créer une demande de certificat pour l’interface externe du serveur de périphérie

1.  Sur le serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3: demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.
    
    <div>
    

    > [!NOTE]  
    > Si votre organisation veut prendre en charge la connectivité de messagerie instantanée publique avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat. À la place, suivez les étapes décrites dans la section «pour créer une demande de certificat pour l’interface externe du serveur Edge pour la prise en charge de la connectivité de messagerie instantanée publique avec AOL», plus loin dans cette rubrique.<BR>Si vous disposez de plusieurs serveurs Edge à un emplacement dans un pool, vous pouvez exécuter l’Assistant Certificat Lync Server 2013 sur l’un des serveurs Edge.

    
    </div>

2.  Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.

3.  Dans la page **demande de certificat** , cliquez sur certificat de **bord externe**.

4.  Dans la page de **demande retardée ou immédiate** , activez la case à cocher **préparer la demande maintenant, puis l’envoyer plus tard** .

5.  Dans la **page fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple,\\c\_:\_CERT l’Edge. cer).

6.  Dans la page **spécifier un modèle de certificat secondaire** , pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre **modèle de certificat pour l’autorité de certification sélectionnée** .

7.  Dans la page **paramètres de nom et de sécurité** , procédez comme suit:
    
      - Dans **nom convivial**, tapez un nom d’affichage pour le certificat.
    
      - En **longueur**, spécifiez la longueur en bits (en général, la valeur par défaut **2048**).
    
      - Vérifiez que la case à cocher **marquer le certificat en tant que clé publique en tant qu’export** est activée.

8.  Dans la page informations sur l' **organisation** , tapez le nom de l’organisation et l’unité d’organisation (par exemple, une division ou un service).

9.  Dans la page **informations géographiques** , spécifiez les informations d’emplacement.

10. Sur la page nom de l’objet **/nom** de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées. Si d’autres noms d’objet sont nécessaires, vous pouvez les spécifier au cours des deux étapes suivantes.

11. Dans la page Configuration du protocole **SIP sur le nom de l’objet** , activez la case à cocher Domain pour ajouter un SIP. \<entrée\> sipdomain dans la liste noms de remplacement de l’objet.

12. Dans la page configurez d’autres **noms d’objet** , spécifiez d’autres noms d’objet obligatoires.

13. Dans la page Résumé de la **demande** , passez en revue les informations de certificat à utiliser pour générer la requête.

14. À la fin de l’exécution de la commande, procédez comme suit:
    
      - Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.
    
      - Pour remplir la demande de certificat, cliquez sur **suivant**.

15. Dans la page **fichier de demande de certificat** , procédez comme suit:
    
      - Pour afficher le fichier de demande de signature de certificat généré (CSR), cliquez sur **Afficher**.
    
      - Pour fermer l’Assistant, cliquez sur **Terminer**.

16. Copiez le fichier de sortie à un emplacement dans lequel vous pouvez le renvoyer à l’autorité de certification publique.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Pour créer une demande de certificat pour l’interface externe du serveur de périphérie pour la prise en charge de la connectivité de messagerie instantanée publique avec AOL

1.  Lorsque le modèle requis est disponible pour l’autorité de certification, utilisez la cmdlet Windows PowerShell suivante à partir du serveur de périphérie pour demander le certificat:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Le nom du certificat par défaut du modèle fourni dans Lync Server 2013 est serveur Web. Spécifiez le \<nom\> du modèle uniquement si vous devez utiliser un modèle différent du modèle par défaut.
    
    <div>
    

    > [!NOTE]  
    > Si votre organisation veut prendre en charge une connectivité de messagerie instantanée publique avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit affecté au bord externe du service Edge d’accès. Ce problème est dû au fait que le modèle de serveur Web 2013 à l’aide de l’Assistant Création de certificat ne prend pas en charge la configuration EKU du client. Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de l’utilisation du client.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>Pour renvoyer une demande auprès d’une autorité de certification publique

1.  Ouvrez le fichier de sortie.

2.  Copiez et collez le contenu de la demande de signature de certificat (CSR).

3.  Si vous y êtes invité, spécifiez les éléments suivants:
    
      - **Microsoft** en tant que plateforme serveur.
    
      - **IIS** en tant que version.
    
      - **Serveur Web** comme type d’utilisation.
    
      - **PKCS7** en tant que format de la réponse.

4.  Lorsque l’AC publique a vérifié vos informations, vous recevez un message électronique contenant un texte requis pour votre certificat.

5.  Copiez le texte du message électronique et enregistrez le contenu dans un fichier texte (. txt) sur votre ordinateur local.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>Pour importer le certificat pour l’interface externe du serveur de périphérie

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez créé la demande de certificat.

2.  Dans l’Assistant Déploiement, dans la page **déploiement du serveur Edge** , en regard de l' **étape 3: demander, installer ou affecter des certificats**, cliquez de nouveau sur **exécuter**.

3.  Dans la page **tâches de certification disponibles** , cliquez sur **Importer un certificat à partir d’un fichier. p7b, pfx ou. cer**.

4.  Sur la page **importer le certificat** , cliquez sur **Parcourir** pour rechercher et sélectionner le certificat que vous avez demandé pour l’interface externe du serveur Edge (ou bien tapez le chemin d’accès complet et le nom du fichier). Si le certificat contient une clé privée, sélectionnez le **fichier de certificat contient la clé privée du certificat** et tapez le mot de passe de la clé privée. Cliquez sur **Suivant**.

5.  Sur la page **importer le résumé du certificat** , examinez le résumé, puis cliquez sur **suivant**.

6.  Sur l' **exécution des commandes**, examinez les résultats de l’importation, puis cliquez sur Afficher le journal pour **Afficher** d’autres informations si nécessaire, puis cliquez sur **Terminer** pour achever l’importation du certificat.

7.  Si vous configurez un pool de serveurs Edge, exportez le certificat avec sa clé privée, comme indiqué dans la procédure «pour exporter le certificat avec la clé privée pour les serveurs Edge dans une liste» plus loin dans cette rubrique. Copiez le fichier de certificat exporté vers les autres serveurs Edge, puis importez-le dans le magasin d’ordinateur sur chaque serveur Edge.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.

2.  Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.

3.  Dans la console Microsoft Management Console (MMC), cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.

4.  Dans **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **certificats**, puis cliquez sur **Ajouter**.

5.  Dans la boîte de dialogue **certificats** , sélectionnez **compte d’ordinateur**, cliquez sur **suivant**, sélectionnez **ordinateur local: (l’ordinateur sur lequel cette console s’exécute)** dans **Sélectionner un ordinateur**, cliquez sur **Terminer** , puis sur **OK** pour configuration complète de la console MMC.

6.  Double-cliquez sur **certificats (ordinateur local)** pour développer les magasins de certificats, double-cliquez sur **personnel**, puis double-cliquez sur **certificats**.
    
    <div>
    

    > [!IMPORTANT]  
    > S’il n’y a aucun certificat dans le magasin personnel de certificats de l’ordinateur local, il n’existe aucune clé privée associée au certificat importé. Passez en revue les étapes de demande et d’importation. Si le problème persiste, contactez votre administrateur ou fournisseur de l’autorité de certification.

    
    </div>

7.  Dans le **magasin personnel de certificats de l’ordinateur local**, cliquez avec le bouton droit sur le certificat que vous exportez, cliquez sur **toutes les tâches**, puis cliquez sur **Exporter**.

8.  Dans l’Assistant exportation de certificat, cliquez sur **suivant**, sélectionnez **Oui, exportez la clé privée**, puis cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si la sélection est <STRONG>Oui, exporter la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’est pas marquée pour l’exportation. Vous devez demander à nouveau le certificat, en veillant à ce que le certificat soit marqué pour autoriser l’exportation de la clé privée avant de poursuivre l’exportation. Contactez votre administrateur ou fournisseur de l’autorité de certification.

    
    </div>

9.  Dans la boîte de dialogue Exporter les formats de fichier, sélectionnez **échange\#d’informations personnelles – PKCS 12 (. PFX)** , puis sélectionnez les options suivantes:
    
      - Incluez tous les certificats dans le chemin de certification, le cas échéant.
    
      - Exporter toutes les propriétés étendues
        
        <div>
        

        > [!WARNING]  
        > Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation est réussie</STRONG>. La sélection de cette option nécessite l’importation du certificat et de la clé privée vers ce serveur Edge.

        
        </div>

10. Cliquez sur **Suivant**.

11. Tapez un mot de passe pour la clé privée, tapez à nouveau le mot de passe pour le confirmer, puis cliquez sur **suivant**.

12. Tapez un chemin d’accès et un nom de fichier avec l’extension .pfx pour le certificat exporté. Le chemin d’accès doit être accessible à tous les autres serveurs de périphérie du pool ou disponible pour le transport par le biais de médias amovibles (par exemple, un lecteur flash USB). Cliquez sur **Suivant**.

13. Passez en revue le résumé pour **terminer l’Assistant exportation de certificat**, puis cliquez sur **Terminer**.

14. Dans la boîte de dialogue exportation réussie, cliquez sur **OK**.

15. Importez le fichier de certificat exporté vers les autres serveurs de périmètre en suivant les étapes décrites dans la procédure «importer le certificat pour l’interface externe de la section serveur Edge» plus haut dans cette rubrique.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>Pour attribuer le certificat pour l’interface externe du serveur de périphérie

1.  Sur chaque serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3: demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.

2.  Dans la page **tâches de certification disponibles** , cliquez sur **attribuer un certificat existant**.

3.  Dans la page **affectation de certificat** , cliquez sur certificat de **périphérie externe** , puis activez la case à cocher **Utilisation avancée des certificats** .

4.  Sur la page **Utilisation avancée du certificat** , activez toutes les cases à cocher pour affecter le certificat à toutes les utilisations.

5.  Dans la page **magasin de certificats** , sélectionnez le certificat public que vous avez demandé et importé pour l’interface externe du serveur Edge.
    
    <div>
    

    > [!NOTE]  
    > Si le certificat que vous avez demandé et importé ne figure pas dans la liste, l’une des méthodes de tournage peut consister à vérifier que le nom de l’objet et le nom de l’objet du certificat répondent à toutes les conditions requises pour le certificat et, si vous avez importé manuellement le certificat et chaîne de certificats au lieu d’utiliser les procédures précédentes, que le certificat se trouve dans le magasin de certificats approprié (le magasin de certificats de l’ordinateur, et non pas le magasin de certificats d’utilisateur ou de service).

    
    </div>

6.  Dans la page Résumé des affectations de **certificat** , passez en revue vos paramètres, puis cliquez sur **suivant** pour attribuer les certificats.

7.  Dans la page de fin de l’Assistant, cliquez sur **Terminer**.

8.  Lorsque vous utilisez cette procédure pour attribuer le certificat de bord, ouvrez le composant logiciel enfichable Certificats sur chaque serveur, développez **certificats (ordinateur local)**, **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que l’option le certificat est répertorié.

9.  Si votre déploiement inclut plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


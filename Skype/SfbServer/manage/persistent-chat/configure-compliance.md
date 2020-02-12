---
title: Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Résumé : Découvrez comment configurer le service de conformité permanent Chat Server dans Skype entreprise Server 2015.'
ms.openlocfilehash: f25df3e85112f91c1286c0be49c428c364acf018
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887843"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="2d9e3-103">Configuration du service de conformité du serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d9e3-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="2d9e3-104">**Résumé :** Apprenez à configurer le service de conformité du serveur Chat permanent dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="2d9e3-105">La conformité de conversation permanente permet aux administrateurs d’archiver les messages de conversation permanente, ainsi que les activités.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="2d9e3-106">Le service de conformité enregistre et archive les données relatives à chaque conversation du serveur de chat permanent, y compris le moment où un participant :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="2d9e3-107">Rejoindre une salle de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="2d9e3-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="2d9e3-108">Quitte une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="2d9e3-108">Leaves a chat room</span></span>

- <span data-ttu-id="2d9e3-109">Publie un message</span><span class="sxs-lookup"><span data-stu-id="2d9e3-109">Posts a message</span></span>

- <span data-ttu-id="2d9e3-110">Consulte l’historique d’une conversation</span><span class="sxs-lookup"><span data-stu-id="2d9e3-110">Views chat history</span></span>

- <span data-ttu-id="2d9e3-111">Transfère un fichier</span><span class="sxs-lookup"><span data-stu-id="2d9e3-111">Uploads a file</span></span>

- <span data-ttu-id="2d9e3-112">Télécharge un fichier</span><span class="sxs-lookup"><span data-stu-id="2d9e3-112">Downloads a file</span></span>

<span data-ttu-id="2d9e3-113">Ces informations sont récupérables au besoin à partir de la base de données SQL de conformité.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="2d9e3-114">La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2d9e3-115">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="2d9e3-116">Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="2d9e3-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="2d9e3-117">Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="2d9e3-118">Configurez le service de conformité à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d9e3-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="2d9e3-119">Une fois que le service de conformité a été activé à l’aide du générateur de topologie, vous pouvez configurer le service à l’aide de l’applet de commande **Set-CsPersistenChatComplianceConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="2d9e3-120">ou</span><span class="sxs-lookup"><span data-stu-id="2d9e3-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="2d9e3-121">Vous pouvez définir les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-121">You can set the following parameters:</span></span>

- <span data-ttu-id="2d9e3-122">AdapterType : permet de définir le type d’adaptateur.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="2d9e3-123">Un adaptateur est un produit tiers qui convertit les données dans la base de données de conformité dans un format spécifique.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="2d9e3-124">XML est le format par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-124">XML is the default.</span></span>

- <span data-ttu-id="2d9e3-125">OneChatRoomPerOutputFile-ce paramètre vous permet de spécifier la création de rapports séparés pour chaque salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="2d9e3-126">AddChatRoomDetails : lorsque ce paramètre est activé, des détails supplémentaires sont enregistrés sur chaque salle de conversation dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="2d9e3-127">Comme ce paramètre peut considérablement augmenter la taille de la base de données, il est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="2d9e3-128">AddUserDetails : lorsque ce paramètre est activé, des détails supplémentaires sont enregistrés sur chaque salle de conversation dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="2d9e3-129">Comme ce paramètre peut considérablement augmenter la taille de la base de données, il est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="2d9e3-130">Identity : ce paramètre permet d’étendre les paramètres de conformité à un ensemble particulier, y compris aux niveaux global, du site et du service.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="2d9e3-131">Il est défini sur le niveau global par défaut.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-131">The default is the global level.</span></span> 

- <span data-ttu-id="2d9e3-132">RunInterval : ce paramètre précise le délai avant que le serveur ne crée un nouveau fichier de sortie de conformité (le délai est défini sur 15 minutes par défaut).</span><span class="sxs-lookup"><span data-stu-id="2d9e3-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="2d9e3-133">Utilisez un adaptateur de conformité personnalisé</span><span class="sxs-lookup"><span data-stu-id="2d9e3-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="2d9e3-134">Vous pouvez écrire un adaptateur personnalisé au lieu d’utiliser le XmlAdapter qui est installé avec le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="2d9e3-135">Pour ce faire, vous devez fournir un assembly .NET Framework contenant une classe publique qui implémente l’interface **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="2d9e3-136">Dans le dossier d’installation serveur Chat permanent de chaque serveur dans votre pool de serveurs chat permanent, vous devez l’installer.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="2d9e3-137">Chacun des serveurs de conformité peut fournir des données de conformité à votre adaptateur, mais ils ne délivrent aucun duplicata des données de conformité à plusieurs instances de votre adaptateur.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="2d9e3-138">L’interface est définie dans l’espace de noms `Microsoft.Rtc.Internal.Chat.Server.Compliance`Compliance. dll.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="2d9e3-139">Elle définit deux méthodes que votre adaptateur personnalisé doit implémenter.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="2d9e3-140">Le serveur de conformité des conversations permanent appelle la méthode suivante lors du premier chargement de la carte.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="2d9e3-141">Le `AdapterConfig` contient la configuration de compatibilité de conversation permanente pertinente pour la carte de conformité :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="2d9e3-142">Le serveur de conformité des conversations permanent appelle la méthode suivante à intervalles réguliers tant qu’il existe de nouvelles données à traduire.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="2d9e3-143">Cet intervalle de temps est égal à `RunInterval` celui défini dans la configuration de conformité des conversations permanentes :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="2d9e3-144">Le `ConversationCollection` contient les informations de conversation collectées à partir de la dernière fois que cette méthode a été appelée.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="2d9e3-145">Personnaliser le fichier de définition XSLT</span><span class="sxs-lookup"><span data-stu-id="2d9e3-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="2d9e3-p111">Les données de conformité sont fournies au format XML, que vous pouvez transformer dans le format le mieux adapté à votre organisation, à l’aide du fichier de définition XSLT. Cette rubrique décrit le fichier XML que le service de conformité crée. Elle fournit également des échantillons de fichiers de définition XSLT et de sortie.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p111">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="2d9e3-149">Format de sortie</span><span class="sxs-lookup"><span data-stu-id="2d9e3-149">Output format</span></span>

<span data-ttu-id="2d9e3-150">La sortie du service de conformité est classée par conversation (l’élément Conversation) puis par message (l’élément Messages), comme illustré dans l’exemple de code suivant :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

<span data-ttu-id="2d9e3-p112">Un élément Conversation contient quatre éléments (Channel, FirstMessage, StartTimeUTC et EndTimeUTC). L’élément Channel contient l’URI (Uniform Resource Identifier) de la salle de conversation et l’élément FirstMessage décrit le premier message de l’élément Messages. Les éléments StartTimeUTC et EndTimeUTC fournissent les heures de début et de fin pour la conversation, comme illustré dans l’exemple de code suivant :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p112">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="2d9e3-p113">Un élément Message contient deux éléments (Sender et DateTimeUTC) et trois attributs (Type, Content et ID). L’élément Sender représente l’utilisateur qui envoie le message, et l’élément DateTimeUTC le moment où se produit un événement, comme illustré dans l’exemple de code suivant :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p113">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="2d9e3-156">Le tableau suivant décrit les attributs de message Type, Content, et ID.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="2d9e3-157">**Attributs de l’élément Messages**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="2d9e3-158">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-158">**Attribute**</span></span>|<span data-ttu-id="2d9e3-159">**Description**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-159">**Description**</span></span>|<span data-ttu-id="2d9e3-160">**Facultatif/obligatoire**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d9e3-161">Type</span><span class="sxs-lookup"><span data-stu-id="2d9e3-161">Type</span></span>  <br/> |<span data-ttu-id="2d9e3-p114">Spécifie le type de message. Les types de message sont décrits dans la table Éléments de message Types de message.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="2d9e3-164">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2d9e3-164">Required</span></span>  <br/> |
|<span data-ttu-id="2d9e3-165">Contenu</span><span class="sxs-lookup"><span data-stu-id="2d9e3-165">Content</span></span>  <br/> |<span data-ttu-id="2d9e3-p115">Contient le contenu du message. Les messages de type Join ou Part n’utilisent pas cet attribut.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="2d9e3-168">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2d9e3-168">Optional</span></span>  <br/> |
|<span data-ttu-id="2d9e3-169">ID</span><span class="sxs-lookup"><span data-stu-id="2d9e3-169">ID</span></span>  <br/> |<span data-ttu-id="2d9e3-p116">Spécifie l’ID unique du contenu. Cet attribut est utilisé uniquement avec les messages de type Chat.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="2d9e3-172">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2d9e3-172">Optional</span></span>  <br/> |

<span data-ttu-id="2d9e3-p117">Chaque élément Sender contient cinq attributs : username, ID, email, internal et URI. Ces attributs sont décrits dans la table suivante.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="2d9e3-175">**Attributs de l’élément Sender**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="2d9e3-176">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-176">**Attribute**</span></span>|<span data-ttu-id="2d9e3-177">**Description**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-177">**Description**</span></span>|<span data-ttu-id="2d9e3-178">**Facultatif/obligatoire**</span><span class="sxs-lookup"><span data-stu-id="2d9e3-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d9e3-179">Nom d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="2d9e3-179">Username</span></span>  <br/> |<span data-ttu-id="2d9e3-180">Nom de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="2d9e3-181">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2d9e3-181">Optional</span></span>  <br/> |
|<span data-ttu-id="2d9e3-182">ID</span><span class="sxs-lookup"><span data-stu-id="2d9e3-182">ID</span></span>  <br/> |<span data-ttu-id="2d9e3-183">ID unique de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="2d9e3-184">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2d9e3-184">Required</span></span>  <br/> |
|<span data-ttu-id="2d9e3-185">Email</span><span class="sxs-lookup"><span data-stu-id="2d9e3-185">Email</span></span>  <br/> |<span data-ttu-id="2d9e3-186">Adresse de messagerie de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="2d9e3-187">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2d9e3-187">Optional</span></span>  <br/> |
|<span data-ttu-id="2d9e3-188">Interne</span><span class="sxs-lookup"><span data-stu-id="2d9e3-188">Internal</span></span>  <br/> |<span data-ttu-id="2d9e3-p118">Détermine si l’utilisateur est un utilisateur interne ou fédéré. Si la valeur est Vraie, l’utilisateur est interne.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="2d9e3-191">Facultatif</span><span class="sxs-lookup"><span data-stu-id="2d9e3-191">Optional</span></span>  <br/> |
|<span data-ttu-id="2d9e3-192">Uri</span><span class="sxs-lookup"><span data-stu-id="2d9e3-192">Uri</span></span>  <br/> |<span data-ttu-id="2d9e3-193">URI SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="2d9e3-194">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="2d9e3-194">Required</span></span>  <br/> |

<span data-ttu-id="2d9e3-195">Les exemples suivants illustrent les types de messages que l’élément message peut contenir.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="2d9e3-196">Elle fournit également des exemples de la manière avec laquelle chaque élément est utilisé.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="2d9e3-197">Joindre-un utilisateur rejoint une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="2d9e3-198">Partie : un utilisateur quitte une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="2d9e3-199">Chat : adresse de messagerie de l’expéditeur.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="2d9e3-200">Messagerie instantanée : un utilisateur demande du contenu à partir de l’historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="2d9e3-201">Chargement de fichiers : un utilisateur charge un fichier.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="2d9e3-202">Téléchargement de fichier-un utilisateur télécharge un fichier.</span><span class="sxs-lookup"><span data-stu-id="2d9e3-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="2d9e3-203">Conversion par défaut de la sortie de conversation permanente et transformation XSL</span><span class="sxs-lookup"><span data-stu-id="2d9e3-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="2d9e3-204">L’exemple de code suivant contient la sortie par défaut du serveur de conformité :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-204">The following code sample contains the default output from the Compliance Server:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="2d9e3-205">L’exemple de code suivant contient un exemple de transformation XSL :</span><span class="sxs-lookup"><span data-stu-id="2d9e3-205">The following code sample contains a sample XSL transform:</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```

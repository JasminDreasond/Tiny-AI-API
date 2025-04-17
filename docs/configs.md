### `setMaxOutputTokens(value, id?)`

Sets the maximum number of output tokens for a given AI session. This method allows developers to control the maximum output length for the AI's responses.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `value` | `number` | The maximum number of output tokens to set. Must be a finite, valid number. |
| `id`    | `string?` | *(Optional)* The session ID to operate on. If omitted, the currently selected session will be used. |

#### Throws

- `Error`: If the `value` is not a valid number (NaN or infinite values are invalid).

#### Returns

- `void`: This method does not return a value.

#### Behavior

- Validates the provided `value` to ensure it is a finite number.
- If valid, updates the session history with the new `maxOutputTokens` setting.
- Emits the `setMaxOutputTokens` event with the new token value and the session ID.

---

### `getMaxOutputTokens(id?)`

Gets the maximum number of output tokens for a given AI session. This method allows developers to retrieve the current token limit for the AI's responses.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `id`   | `string?` | *(Optional)* The session ID to operate on. If omitted, the currently selected session will be used. |

#### Returns

- `number | null`: The maximum output tokens value if it is set. If not set, returns `null`.

#### Behavior

- Checks the session's history for the `maxOutputTokens` value.
- If the value exists and is a valid number, it returns the token limit.
- If the value is not set or is invalid, it returns `null`.

---

### `setTemperature(value, id?)`

Sets the temperature setting for a given AI session. The temperature value controls the randomness of the AI's responses, with higher values generating more random outputs and lower values making the responses more deterministic.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `value` | `number` | The temperature value to be set. Must be a finite, valid number. |
| `id`    | `string?` | *(Optional)* The session ID to operate on. If omitted, the currently selected session will be used. |

#### Throws

- `Error`: If the `value` is not a valid number (NaN or infinite values are invalid).

#### Returns

- `void`: This method does not return a value.

#### Behavior

- Validates the provided `value` to ensure it is a finite number.
- If valid, updates the session history with the new `temperature` setting.
- Emits the `setTemperature` event with the new temperature value and the session ID.

---

### `getTemperature(id?)`

Retrieves the temperature setting for a given AI session. The temperature controls the randomness of the AI's responses. If not set, it returns `null`.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `id`    | `string?` | *(Optional)* The session ID to operate on. If omitted, the currently selected session will be used. |

#### Returns

- `number | null`: The temperature value if set, otherwise `null`.

#### Behavior

- Retrieves the `temperature` value from the session history. 
- If the `temperature` value is not set, it returns `null`.

---

### `setTopP(value, id?)`

Sets the top-p (nucleus sampling) value for a given AI session. The top-p value controls the diversity of the output by considering the smallest set of tokens whose cumulative probability is greater than the top-p value.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `value` | `number`  | The top-p value to be set. It must be a finite number. |
| `id`    | `string?` | *(Optional)* The session ID to operate on. If omitted, the currently selected session will be used. |

#### Returns

- `void`: This function does not return a value.

#### Behavior

- Validates that `value` is a finite number.
- Sets the top-p value in the session's history.
- Emits an event named `setTopP` with the `value` and `selectedId`.

#### Throws

- Throws an error if the `value` is not a valid number.

---

### `getTopP(id?)`

Retrieves the top-p (nucleus sampling) value for a given AI session. The top-p value controls the diversity of the output by considering the smallest set of tokens whose cumulative probability is greater than the top-p value.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `id`    | `string?` | *(Optional)* The session ID to retrieve the top-p value for. If omitted, the currently selected session will be used. |

#### Returns

- `number | null`: The top-p value if it is set, or `null` if not set.

#### Behavior

- Retrieves the `topP` value from the session's history.
- If the value exists and is a valid number, it will return the value.
- If no valid value is found, it will return `null`.

---

### `setTopK(value, id?)`

Sets the top-k value for a given AI session. The top-k value determines how many of the highest probability tokens are considered when generating output.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `value` | `number`  | The top-k value to be set. Must be a valid number. |
| `id`    | `string?` | *(Optional)* The session ID to set the top-k value for. If omitted, the currently selected session will be used. |

#### Returns

- `void`: This method does not return a value.

#### Throws

- Throws an error if the provided `value` is not a valid number.

#### Behavior

- Sets the `topK` value in the session's history for the specified session.
- Emits a `setTopK` event with the provided value and the session ID.

---

### `getTopK(id?)`

Retrieves the top-k value for a given AI session. The top-k value represents the number of highest probability tokens considered during output generation.

#### Parameters

| Name   | Type      | Description |
|--------|-----------|-------------|
| `id`    | `string?` | *(Optional)* The session ID to retrieve the top-k value for. If omitted, the currently selected session will be used. |

#### Returns

- `number | null`: Returns the `topK` value if set for the session, or `null` if the top-k value is not set.

#### Behavior

- Retrieves the `topK` value from the session's history for the specified session.

---

### `setPresencePenalty(value, id?)`

Sets the presence penalty value for a given AI session. The presence penalty influences how much the model avoids generating tokens that have appeared in the context.

#### Parameters

| Name    | Type      | Description |
|---------|-----------|-------------|
| `value`  | `number`  | The presence penalty value to be set. Must be a valid number. |
| `id`     | `string?` | *(Optional)* The session ID for which to set the presence penalty. If omitted, the currently selected session will be used. |

#### Returns

- `void`: This function does not return a value.

#### Behavior

- Sets the `presencePenalty` in the session's history for the specified session.

---

### `getPresencePenalty(id?)`

Retrieves the presence penalty setting for a given AI session. The presence penalty helps control how much the model avoids repeating tokens already seen in the context.

#### Parameters

| Name    | Type      | Description |
|---------|-----------|-------------|
| `id`     | `string?` | *(Optional)* The session ID for which to retrieve the presence penalty. If omitted, the currently selected session will be used. |

#### Returns

- `number | null`: Returns the presence penalty value if set, or `null` if no value is set.

#### Behavior

- Retrieves the `presencePenalty` from the session's history for the specified session.

---

### `setFrequencyPenalty(value, id?)`

Sets the frequency penalty setting for an AI session. The frequency penalty helps to penalize models for repeating the same tokens or phrases, allowing for more diverse responses.

#### Parameters

| Name     | Type      | Description |
|----------|-----------|-------------|
| `value`  | `number`  | The frequency penalty value to be set. This value should be a number. |
| `id`     | `string?` | *(Optional)* The session ID. If omitted, the currently selected session will be used. |

#### Returns

- `void`: This function does not return a value.

#### Behavior

- If the provided `value` is a valid number, the method sets the `frequencyPenalty` in the session's history.
- Emits the `setFrequencyPenalty` event with the value and selected session ID.
- Throws an error if the `value` is not a valid number.

---

### `getFrequencyPenalty(id?)`

Retrieves the frequency penalty setting for an AI session. The frequency penalty is used to penalize models for repeating the same tokens or phrases, helping to ensure more varied responses.

#### Parameters

| Name     | Type      | Description |
|----------|-----------|-------------|
| `id`     | `string?` | *(Optional)* The session ID. If omitted, the currently selected session will be used. |

#### Returns

- `number | null`: The frequency penalty value, or `null` if the value is not set for the session.

#### Behavior

- If the `frequencyPenalty` is set in the session's history, the method returns its value.
- If the value is not set or not found, the method returns `null`.

---

### `setEnabledEnchancedCivicAnswers(value, id?)`

Sets the setting for enabling enhanced civic answers in an AI session. This setting determines whether the AI should provide enhanced civic answers, typically involving more detailed, accurate, and contextually relevant responses related to civic topics.

#### Parameters

| Name     | Type      | Description |
|----------|-----------|-------------|
| `value`  | `boolean` | A boolean value to enable or disable enhanced civic answers. Set to `true` to enable, or `false` to disable. |
| `id`     | `string?` | *(Optional)* The session ID. If omitted, the currently selected session will be used. |

#### Returns

- This function does not return any value.

#### Behavior

- If the provided `value` is a boolean, the setting is updated for the specified session.
- If the `value` is not a boolean, an error is thrown with the message `'Invalid boolean value!'`.

---

### `isEnabledEnchancedCivicAnswers(id?)`

Gets the setting for whether enhanced civic answers are enabled in an AI session. This setting indicates whether the AI is configured to provide enhanced civic answers, which might involve more accurate or contextually relevant responses on civic topics.

#### Parameters

| Name     | Type      | Description |
|----------|-----------|-------------|
| `id`     | `string?` | *(Optional)* The session ID. If omitted, the currently selected session will be used. |

#### Returns

- `boolean` if the setting is enabled or disabled (`true` or `false`).
- `null` if the setting has not been set for the session.

#### Behavior

- If the setting for enhanced civic answers is available and is a boolean, it will be returned.
- If the setting is not available or not set, it returns `null`.

---

### `setApiKey(apiKey)`

Sets the API key to be used for the AI session.

#### Parameters

| Name      | Type     | Description                |
|-----------|----------|----------------------------|
| `apiKey`  | `string` | The API key to be stored.  |

#### Returns

- **`void`**: This method does not return any value.

#### Behavior

- Stores the provided `apiKey` if it's a string.
- If the value is not a string, it sets the internal key to `null`.

> **Note:** This key is stored internally and is not associated with any session history.

---

### `setPrompt(promptData, tokenAmount, id)`

Sets a prompt for the selected session history.

---

#### Parameters

| Name          | Type      | Required | Description                                                                 |
|---------------|-----------|----------|-----------------------------------------------------------------------------|
| `promptData`  | `string`  | Yes      | The prompt to be set for the session. This must be a string.                |
| `tokenAmount` | `number`  | No       | The number of tokens associated with the prompt (optional).                 |
| `id`          | `string`  | No       | The session ID. If omitted, the currently selected session will be used.    |

---

#### Throws

| Type     | Description                                                      |
|----------|------------------------------------------------------------------|
| `Error`  | Thrown if the provided session ID is invalid or if `promptData` is not a string. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session history exists for the selected session and `promptData` is a valid string:
  - It sets the `prompt` in the session history.
  - It hashes the `promptData` and stores the hash in `hash.prompt`.
  - If `tokenAmount` is provided and is a valid number, it associates the `tokenAmount` with the prompt.
- Emits the `setPrompt` event with the prompt data and the session ID.

---

#### Implementation

```js
setPrompt(promptData, tokenAmount, id) {
  const selectedId = this.getId(id);
  if (this.history[selectedId]) {
    if (typeof promptData === 'string') {
      const hash = objHash(promptData);
      this.history[selectedId].prompt = promptData;
      this.history[selectedId].hash.prompt = hash;
    }

    if (typeof tokenAmount === 'number') this.history[selectedId].tokens.prompt = tokenAmount;
    this.emit('setPrompt', promptData, selectedId);
    return;
  }
  throw new Error('Invalid history id data!');
}
```

---

#### Example Usage

```js
try {
  const prompt = "Please enter your query";
  const tokenCount = 10;
  sessionManager.setPrompt(prompt, tokenCount);
  console.log("Prompt has been set successfully.");
} catch (error) {
  console.error(error.message);
}
```

This method is used to assign a prompt to a specific session, optionally associating token data with it. It ensures the prompt is a string and the session ID is valid, allowing the prompt and token data to be stored within the session history.

---

### `getPrompt(id)`

Retrieves the prompt of the selected session history.

---

#### Parameters

| Name    | Type     | Required | Description                                                                 |
|---------|----------|----------|-----------------------------------------------------------------------------|
| `id`    | `string` | No       | The session ID. If omitted, the currently selected session will be used.    |

---

#### Returns

| Type    | Description                                                                 |
|---------|-----------------------------------------------------------------------------|
| `string`| The prompt for the session if available.                                    |
| `null`  | Returns `null` if no prompt exists for the selected session.                |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session history exists for the selected session and the `prompt` is a non-empty string, it returns the prompt.
- If no valid prompt exists, it returns `null`.

---

#### Implementation

```js
getPrompt(id) {
  const selectedId = this.getId(id);
  if (
    this.history[selectedId] &&
    typeof this.history[selectedId].prompt === 'string' &&
    this.history[selectedId].prompt.length > 0
  ) {
    return this.history[selectedId].prompt;
  }
  return null;
}
```

---

#### Example Usage

```js
const prompt = sessionManager.getPrompt();
if (prompt) {
  console.log("Current session prompt: " + prompt);
} else {
  console.log("No prompt available for the current session.");
}
```

This method retrieves the prompt of the selected session, returning the prompt string if it exists, or `null` if no valid prompt is found. It ensures that the prompt is a non-empty string before returning it.

---

### `setFirstDialogue(dialogue, tokenAmount, id)`

Sets the first dialogue for the selected session history.

---

#### Parameters

| Name         | Type     | Required | Description                                                                 |
|--------------|----------|----------|-----------------------------------------------------------------------------|
| `dialogue`   | `string` | Yes      | The dialogue to set as the first dialogue for the session.                   |
| `tokenAmount`| `number` | No       | The number of tokens associated with the dialogue (optional).               |
| `id`         | `string` | No       | The session ID. If omitted, the currently selected session will be used.    |

---

#### Returns

| Type    | Description                                                                 |
|---------|-----------------------------------------------------------------------------|
| `void`  | This method does not return any value. It throws an error if the session ID is invalid or if the dialogue is not a string. |

---

#### Throws

- Throws an error if the session ID is invalid or if the provided dialogue is not a string.

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session history exists for the selected session and the `dialogue` is a valid string, the first dialogue is set and the corresponding hash is stored.
- Optionally, if a `tokenAmount` is provided, the number of tokens associated with the dialogue is set.
- Emits the `setFirstDialogue` event with the `dialogue` and the `selectedId`.

---

#### Implementation

```js
setFirstDialogue(dialogue, tokenAmount, id) {
  const selectedId = this.getId(id);
  if (this.history[selectedId]) {
    if (typeof dialogue === 'string') {
      const hash = objHash(dialogue);
      this.history[selectedId].firstDialogue = dialogue;
      this.history[selectedId].hash.firstDialogue = hash;
    }

    if (typeof tokenAmount === 'number')
      this.history[selectedId].tokens.firstDialogue = tokenAmount;
    this.emit('setFirstDialogue', dialogue, selectedId);
    return;
  }
  throw new Error('Invalid history id data!');
}
```

---

#### Example Usage

```js
try {
  sessionManager.setFirstDialogue("Hello, how can I help you today?", 10);
  console.log("First dialogue set successfully.");
} catch (error) {
  console.error("Error setting first dialogue: " + error.message);
}
```

This method allows you to set the first dialogue for the selected session, associating it with an optional token amount. It also ensures that the provided `dialogue` is a valid string before proceeding.

---

### `getFirstDialogue(id)`

Retrieves the first dialogue from the selected session history.

---

#### Parameters

| Name   | Type     | Required | Description                                                                 |
|--------|----------|----------|-----------------------------------------------------------------------------|
| `id`   | `string` | No       | The session ID. If omitted, the currently selected session history ID will be used. |

---

#### Returns

| Type    | Description                                                                 |
|---------|-----------------------------------------------------------------------------|
| `string`| The first dialogue from the session history if it exists and is a non-empty string. |
| `null`  | If no first dialogue is set or the first dialogue is empty or invalid. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session history exists for the selected session and the first dialogue is a valid string, it returns the first dialogue.
- If no first dialogue is set or the value is empty/invalid, it returns `null`.

---

#### Implementation

```js
getFirstDialogue(id) {
  const selectedId = this.getId(id);
  if (
    this.history[selectedId] &&
    typeof this.history[selectedId].firstDialogue === 'string' &&
    this.history[selectedId].firstDialogue.length > 0
  ) {
    return this.history[selectedId].firstDialogue;
  }
  return null;
}
```

---

#### Example Usage

```js
const firstDialogue = sessionManager.getFirstDialogue();
if (firstDialogue) {
  console.log("First dialogue:", firstDialogue);
} else {
  console.log("No first dialogue set.");
}
```

This method allows you to retrieve the first dialogue from the selected session. If the first dialogue exists and is a valid non-empty string, it will be returned; otherwise, `null` will be returned.

---

### `setFileData(mime, data, isBase64, tokenAmount, id)`

Sets file data for the selected session history.

---

#### Parameters

| Name        | Type      | Required | Description                                                                                               |
|-------------|-----------|----------|-----------------------------------------------------------------------------------------------------------|
| `mime`      | `string`  | Yes      | The MIME type of the file (e.g., 'text/plain', 'application/pdf').                                         |
| `data`      | `string`  | Yes      | The file content, either as a string or base64-encoded.                                                    |
| `isBase64`  | `boolean` | No       | A flag indicating whether the `data` is already base64-encoded. Defaults to `false`.                      |
| `tokenAmount`| `number` | No       | The token count associated with the file data (optional).                                                 |
| `id`        | `string`  | No       | The session ID. If omitted, the currently selected session history ID will be used.                       |

---

#### Returns

| Type   | Description |
|--------|-------------|
| `void` | This method does not return a value. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session ID is valid, it processes the `mime`, `data`, and optionally the `isBase64` and `tokenAmount` values.
- The file data is stored in the session history under the `file` property, and the base64 encoding is performed if necessary.
- The file data and hash are then stored in the session history, and the `setFileData` event is emitted.
- If an invalid session ID or data/mime type is provided, an error is thrown.

---

#### Example Usage

```js
sessionManager.setFileData(
  'application/pdf', 
  'file_content_in_base64_or_plain_text', 
  true, 
  123, 
  'session123'
);
```

This would set the file data for the session with ID `'session123'`, using the MIME type `'application/pdf'` and associating the file with a token count of 123.

---

#### Implementation

```js
setFileData(mime, data, isBase64 = false, tokenAmount = undefined, id = undefined) {
  const selectedId = this.getId(id);
  if (this.history[selectedId]) {
    let hash;
    if (typeof data === 'string' && typeof mime === 'string') {
      this.history[selectedId].file = {
        mime,
        data,
        base64: !isBase64 ? Base64.encode(data) : data,
      };
      hash = objHash(this.history[selectedId].file);
      this.history[selectedId].hash.file = hash;
    }

    if (typeof tokenAmount === 'number') this.history[selectedId].tokens.file = tokenAmount;
    this.emit('setFileData', this.history[selectedId].file, hash, selectedId);
    return;
  }
  throw new Error('Invalid history id data!');
}
```

---

This method allows you to store file data (either as raw text or base64-encoded) along with an optional MIME type and token count in a selected session history. It also calculates a hash for the file data and emits an event with the new file data.

---

### `removeFileData(id)`

Removes file data from the selected session history.

---

#### Parameters

| Name        | Type     | Required | Description                                                                                   |
|-------------|----------|----------|-----------------------------------------------------------------------------------------------|
| `id`        | `string` | No       | The session ID. If omitted, the currently selected session history ID will be used.            |

---

#### Returns

| Type   | Description |
|--------|-------------|
| `void` | This method does not return a value. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session ID is valid, it deletes the `file`, `hash.file`, and `tokens.file` properties from the session's history.
- The `setFileData` event is emitted with `null` values, indicating the removal of the file data.
- If an invalid session ID is provided, an error is thrown.

---

#### Example Usage

```js
sessionManager.removeFileData('session123');
```

This would remove the file data from the session with ID `'session123'`.

---

#### Implementation

```js
removeFileData(id) {
  const selectedId = this.getId(id);
  if (this.history[selectedId]) {
    delete this.history[selectedId].file;
    delete this.history[selectedId].hash.file;
    delete this.history[selectedId].tokens.file;
    this.emit('setFileData', null, null, selectedId);
    return;
  }
  throw new Error('Invalid history id data!');
}
```

---

This method allows you to remove any stored file data from a specific session's history, including the file content, its hash, and associated token data. It also emits an event to indicate that the file data has been removed.

---

### `getFileData(id)`

Retrieves file data from the selected session history.

---

#### Parameters

| Name        | Type     | Required | Description                                                                                   |
|-------------|----------|----------|-----------------------------------------------------------------------------------------------|
| `id`        | `string` | No       | The session ID. If omitted, the currently selected session history ID will be used.            |

---

#### Returns

| Type      | Description                                                      |
|-----------|------------------------------------------------------------------|
| `Object`  | The file data, including MIME type and encoded content, or `null` if no file data is found. |

---

#### Throws

| Type      | Description                                                 |
|-----------|-------------------------------------------------------------|
| `Error`   | If no valid session history ID is found.                    |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session is valid and contains file data with valid MIME and data fields (both of type string), it returns the file data, which includes:
  - `mime`: The MIME type of the file (e.g., `'text/plain'`, `'application/pdf'`).
  - `data`: The base64-encoded file content.
- If the session history does not contain valid file data, it returns `null`.
- If an invalid session ID is provided, an error is thrown.

---

#### Example Usage

```js
const fileData = sessionManager.getFileData('session123');
if (fileData) {
  console.log(fileData.mime);  // e.g., 'application/pdf'
  console.log(fileData.data);  // base64-encoded content
} else {
  console.log('No file data found');
}
```

This would retrieve and display the MIME type and base64-encoded content of the file data from the session with ID `'session123'`, or display `'No file data found'` if no file data exists.

---

#### Implementation

```js
getFileData(id) {
  const selectedId = this.getId(id);
  if (
    this.history[selectedId] &&
    this.history[selectedId].file &&
    typeof this.history[selectedId].file.data === 'string' &&
    typeof this.history[selectedId].file.mime === 'string'
  ) {
    return this.history[selectedId].file;
  }
  return null;
}
```

---

This method provides access to the file data stored in the selected session's history, including the MIME type and the base64-encoded content of the file. If no valid file data exists, it returns `null`.

---

### `setSystemInstruction(data, tokenAmount, id)`

Sets a system instruction for the selected session history.

---

#### Parameters

| Name             | Type     | Required | Description                                                                                  |
|------------------|----------|----------|----------------------------------------------------------------------------------------------|
| `data`           | `string` | Yes      | The system instruction to set for the session. This should be a string containing the instruction. |
| `tokenAmount`    | `number` | No       | The token count associated with the system instruction (optional).                             |
| `id`             | `string` | No       | The session ID. If omitted, the currently selected session history ID will be used.           |

---

#### Returns

| Type   | Description                               |
|--------|-------------------------------------------|
| `void` | This method does not return a value.      |

---

#### Throws

| Type    | Description                                                            |
|---------|------------------------------------------------------------------------|
| `Error` | If the session history ID is invalid or the provided `data` is not a string. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session is valid and the provided `data` is a string, the system instruction is set for the selected session.
- The hash of the system instruction is computed and stored in the session history.
- If a `tokenAmount` is provided, it is associated with the system instruction.
- If the session history ID is invalid or the provided `data` is not a string, an error is thrown.
- Emits an event `'setSystemInstruction'` with the instruction data and the selected session ID.

---

#### Example Usage

```js
try {
  sessionManager.setSystemInstruction('Ensure system stability', 200, 'session123');
  console.log('System instruction set successfully');
} catch (error) {
  console.log('Error:', error.message);
}
```

This would set the system instruction `'Ensure system stability'` for the session with ID `'session123'`, and associate a token count of `200`. If an error occurs (e.g., if the session ID is invalid), it will be caught and logged.

---

#### Implementation

```js
setSystemInstruction(data, tokenAmount, id) {
  const selectedId = this.getId(id);
  if (this.history[selectedId]) {
    if (typeof data === 'string') {
      const hash = objHash(data);
      this.history[selectedId].systemInstruction = data;
      this.history[selectedId].hash.systemInstruction = hash;
    }

    if (typeof tokenAmount === 'number')
      this.history[selectedId].tokens.systemInstruction = tokenAmount;
    this.emit('setSystemInstruction', data, selectedId);
    return;
  }
  throw new Error('Invalid history id data!');
}
```

---

This method allows you to set a system instruction for a given session, optionally associating token data with it. The session is identified by its history ID, and it throws an error if the provided session ID or data is invalid.

---

### `getSystemInstruction(id)`

Retrieves the system instruction for the selected session history.

---

#### Parameters

| Name    | Type     | Required | Description                                                                                      |
|---------|----------|----------|--------------------------------------------------------------------------------------------------|
| `id`    | `string` | No       | The session ID. If omitted, the currently selected session history ID will be used.              |

---

#### Returns

| Type         | Description                                                          |
|--------------|----------------------------------------------------------------------|
| `string|null` | The system instruction for the selected session, or `null` if no instruction is set. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session exists and the `systemInstruction` is a string, it returns the system instruction for the session.
- If no system instruction is found, it returns `null`.
- If the session history ID is invalid or no system instruction exists, it will return `null`.

---

#### Example Usage

```js
const instruction = sessionManager.getSystemInstruction('session123');
if (instruction) {
  console.log('System Instruction:', instruction);
} else {
  console.log('No system instruction set for this session.');
}
```

This would attempt to retrieve the system instruction for the session with ID `'session123'`. If a system instruction exists, it is logged; otherwise, a message indicating no instruction is set is shown.

---

#### Implementation

```js
getSystemInstruction(id) {
  const selectedId = this.getId(id);
  if (
    this.history[selectedId] &&
    typeof this.history[selectedId].systemInstruction === 'string'
  ) {
    return this.history[selectedId].systemInstruction;
  }
  return null;
}
```

---

This method allows you to retrieve the system instruction for a specified session. If no instruction is found or the session ID is invalid, it will return `null`.

---

### `getTokens(where, id)`

Retrieves the token count for a specific category within the selected session history.

---

#### Parameters

| Name    | Type     | Required | Description                                                                                      |
|---------|----------|----------|--------------------------------------------------------------------------------------------------|
| `where` | `string` | Yes      | The category from which to retrieve the token count (e.g., 'prompt', 'file', 'systemInstruction'). |
| `id`    | `string` | No       | The session ID. If omitted, the currently selected session history ID will be used.              |

---

#### Returns

| Type         | Description                                                          |
|--------------|----------------------------------------------------------------------|
| `number|null` | The token count for the specified category if available, otherwise `null`. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session exists and the specified category (e.g., `prompt`, `file`, or `systemInstruction`) has a token count available, it returns the token count.
- If no token count is available for the category or the session history ID is invalid, it returns `null`.

---

#### Example Usage

```js
const promptTokens = sessionManager.getTokens('prompt', 'session123');
if (promptTokens !== null) {
  console.log('Prompt Token Count:', promptTokens);
} else {
  console.log('No token count found for prompt in this session.');
}
```

This would attempt to retrieve the token count for the `prompt` category in the session with ID `'session123'`. If a token count exists, it is logged; otherwise, a message indicating no token count is found is shown.

---

#### Implementation

```js
getTokens(where, id) {
  const selectedId = this.getId(id);
  if (this.history[selectedId] && typeof this.history[selectedId].tokens[where] === 'number')
    return this.history[selectedId].tokens[where];
  return null;
}
```

---

This method allows you to retrieve the token count for a specific category (such as `prompt`, `file`, or `systemInstruction`) for the selected session. If the token count is not available or the session ID is invalid, it returns `null`.

---

### `getHash(where, id)`

Retrieves the hash value for a specific item in the selected session history.

---

#### Parameters

| Name    | Type     | Required | Description                                                                                       |
|---------|----------|----------|---------------------------------------------------------------------------------------------------|
| `where` | `string` | Yes      | The key representing the item whose hash value is being retrieved (e.g., 'prompt', 'file', 'systemInstruction'). |
| `id`    | `string` | No       | The session ID. If omitted, the currently selected session history ID will be used.               |

---

#### Returns

| Type         | Description                                                   |
|--------------|---------------------------------------------------------------|
| `string|null` | The hash value of the specified item if available, otherwise `null`. |

---

#### Behavior

- Uses `this.getId(id)` to retrieve the selected session ID.
- If the session exists and the specified item (e.g., `prompt`, `file`, `systemInstruction`) has an associated hash value, it returns that hash.
- If no hash value is available for the specified item or the session ID is invalid, it returns `null`.

---

#### Example Usage

```js
const promptHash = sessionManager.getHash('prompt', 'session123');
if (promptHash !== null) {
  console.log('Prompt Hash:', promptHash);
} else {
  console.log('No hash found for prompt in this session.');
}
```

This would attempt to retrieve the hash value for the `prompt` item in the session with ID `'session123'`. If a hash exists, it is logged; otherwise, a message indicating no hash is found is displayed.

---

#### Implementation

```js
getHash(where, id) {
  const selectedId = this.getId(id);
  if (this.history[selectedId] && typeof this.history[selectedId].hash[where] === 'string')
    return this.history[selectedId].hash[where];
  return null;
}
```

---

This method allows you to retrieve the hash value for a specific item (such as `prompt`, `file`, or `systemInstruction`) in the selected session. If the hash is not available or the session ID is invalid, it returns `null`.

---

### `startDataId(id, selected = false)`

Starts a new data session with the given session ID.

---

#### Parameters

| Name        | Type     | Required | Description                                                                                   |
|-------------|----------|----------|-----------------------------------------------------------------------------------------------|
| `id`        | `string` | Yes      | The session ID for the new data session.                                                      |
| `selected`  | `boolean`| No       | A flag to indicate whether this session should be selected as the active session. Defaults to `false`. |

---

#### Returns

| Type   | Description                                                      |
|--------|------------------------------------------------------------------|
| `Object` | The newly created session data, which includes:                  |
|         | - `data`: An empty array for storing data.                       |
|         | - `ids`: An empty array for storing IDs.                         |
|         | - `tokens`: An object with an empty `data` array.                |
|         | - `hash`: An object with an empty `data` array.                  |
|         | - `systemInstruction`: A `null` value indicating no system instruction set. |
|         | - `model`: A `null` value indicating no model set.               |

---

#### Behavior

- Creates a new session entry in the `history` object with the provided `id`.
- Initializes the session with empty arrays for `data`, `ids`, `tokens.data`, and `hash.data`, and sets `systemInstruction` and `model` to `null`.
- If the `selected` flag is `true`, it selects the new session as the active session by calling `selectDataId(id)`.
- Emits a `startDataId` event with the newly created session data, session ID, and the selection flag.
- Returns the newly created session data.

---

#### Example Usage

```js
const newSession = sessionManager.startDataId('session123', true);
console.log(newSession);
```

This would start a new data session with the ID `'session123'`, select it as the active session, and log the newly created session data.

---

#### Implementation

```js
startDataId(id, selected = false) {
  this.history[id] = {
    data: [],
    ids: [],
    tokens: { data: [] },
    hash: { data: [] },
    systemInstruction: null,
    model: null,
  };
  if (selected) this.selectDataId(id);
  this.emit('startDataId', this.history[id], id, selected ? true : false);
  return this.history[id];
}
```

---

This method is responsible for initializing a new session with a specific session ID and optional selection flag. It ensures that each session has default, empty structures ready to hold data and other session-specific information. The event `startDataId` is emitted when the session is created.

---

### `stopDataId(id)`

Stops the data session associated with the provided ID. This will remove the session data from history and reset the selected session ID if necessary.

---

#### Parameters

| Name  | Type     | Required | Description                                                       |
|-------|----------|----------|-------------------------------------------------------------------|
| `id`  | `string` | Yes      | The session history ID to stop and remove from history.           |

---

#### Returns

| Type    | Description                                      |
|---------|--------------------------------------------------|
| `boolean` | Returns `true` if the session ID was found and successfully stopped, or `false` otherwise. |

---

#### Behavior

- Removes the session data from the `history` object using the provided `id`.
- If the session being stopped is currently the selected session (i.e., if `getId()` equals `id`), the selected session ID is reset by calling `selectDataId(null)`.
- Emits a `stopDataId` event with the session ID.
- Returns `true` if the session was found and successfully stopped, or `false` if no session with the provided ID exists in the `history`.

---

#### Example Usage

```js
const wasStopped = sessionManager.stopDataId('session123');
if (wasStopped) {
  console.log('Session successfully stopped');
} else {
  console.log('Session ID not found');
}
```

In this example, the session with ID `'session123'` will be stopped and removed from the history. The success or failure of the operation is logged based on whether the session was found.

---

#### Implementation

```js
stopDataId(id) {
  if (this.history[id]) {
    delete this.history[id];
    if (this.getId() === id) this.selectDataId(null);
    this.emit('stopDataId', id);
    return true;
  }
  return false;
}
```

---

This method is used to stop and remove a data session by its ID, ensuring that the session history is properly updated. If the stopped session is the active one, it clears the active session as well.